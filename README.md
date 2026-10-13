# BI_Project_Healthcare-Patient_Appointment_Booking_System
End to End BI project: End-to-end BI project: wrote a full BRD (36 functional requirements, 22 user stories, traceability matrix etc) and analysed 110K+ clinic appointments in Python using pandas to set a 20.2% no-show baseline KPI, identify lead time as the key risk driver, expose a confounded SMS result, and map insights to requirements.
## 1. Business problem
Clinics that take bookings by phone and paper register cannot see missed appointments until the slot is already wasted. Patients cannot book after hours, receptionists are overloaded, and no reminders are sent. Each no-show is idle doctor capacity that cannot be recovered.
## 2. Project at a glance
| Dataset | 110,527 appointments, 14 fields (Kaggle: *Medical Appointment No Shows*, Brazil, 2016) |
| Clean dataset | 110,521 appointments (6 invalid records removed and logged) |
| **Baseline KPI** | **20.2% no-show rate** (BO-1) |
| Requirements | 7 business objectives, 36 functional and 20 non-functional requirements, 7 business rules, 22 user stories, 8 exception flows, traceability matrix |
| Tools | Python (pandas, NumPy, matplotlib, seaborn), Jupyter, Microsoft Word (BRD), draw.io |
## 3. Approach
1. **Requirements (BRD):** defined roles, objectives and KPIs, as-is and to-be process maps, functional and non-functional requirements (MoSCoW), business rules, appointment status lifecycle, user stories with acceptance criteria, exception flows and a requirements traceability matrix.
2. **Data quality:** standardised column names, parsed dates, derived booking lead time, removed impossible values with every rule logged
3. **Analysis:** measured no-show **rates** (not raw counts) by age, gender, conditions, neighbourhood, weekday, lead time, SMS status and patient history, each against the overall baseline.
4. **Validation:** tested whether the apparent SMS effect survives a lead-time control.
## 4. Key findings
**1. One in five appointments is missed.** The baseline no-show rate is **20.2%**, which is the figure the new system's BO-1 target should be measured against.
**2. Lead time is the clearest driver.** Patients who miss appointments waited on average **15.8 days** between booking and visit, compared with **8.8 days** for patients who attended. Same-day appointments have the lowest risk, and risk rises as the booking window lengthens.
**3. Age matters.** Teenagers and young adults show the highest no-show rates; seniors show the lowest.
**4. The SMS result needs careful reading.** Patients who received an SMS had a *higher* no-show rate (**27.6%**) than those who did not (**16.7%**).
This does not mean reminders hurt attendance. In this dataset, SMS reminders are sent mainly on appointments booked well in advance, which are the highest-risk bookings regardless. The notebook therefore compares SMS vs no-SMS **within each lead-time band**. Observational data cannot establish cause, so the recommendation is a controlled pilot rather than a claim.



