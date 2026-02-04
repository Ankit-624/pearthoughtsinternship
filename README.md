Table User {
  user_id int [pk]
  name varchar
  email varchar
  phone varchar
  password varchar
  role varchar
}

Table Doctor {
  doctor_id int [pk]
  specialization varchar
  experience int
  consultation_fee float
  user_id int [ref: > User.user_id]
}

Table Patient {
  patient_id int [pk]
  age int
  gender varchar
  medical_notes varchar
  user_id int [ref: > User.user_id]
}

Table Appointment {
  appointment_id int [pk]
  appointment_date date
  appointment_time time
  status varchar
  reason_for_visit varchar
  doctor_id int [ref: > Doctor.doctor_id]
  patient_id int [ref: > Patient.patient_id]
}

Table Appointment_Slot {
  slot_id int [pk]
  date date
  start_time time
  end_time time
  is_available boolean
  doctor_id int [ref: > Doctor.doctor_id]
}

Table Chat_Message {
  message_id int [pk]
  message_text varchar
  timestamp datetime
  sender_type varchar
  appointment_id int [ref: > Appointment.appointment_id]
}

Table Appointment_History {
  history_id int [pk]
  action_type varchar
  action_time datetime
  previous_date date
  previous_time time
  new_date date
  new_time time
  appointment_id int [ref: > Appointment.appointment_id]
}
