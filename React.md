บ้างทีก็เกียดเขียนซ้ำๆ
```jsx
// Bad
<ul>
  <li>A</li>
  <li>B</li>
  <li>C</li>
  <li>D</li>
<ul>

// Good
<ul>
  {
    ['A', 'B', 'C', 'D'].map((alphabet)=>
      <li key={alphabet}>{alphabet}</li>
    )
  }
<ul>
```

#### จะ import อะไรเยอะแยะ
```jsx
// Bad
import {Login} from './components'
import {ForgotPassword} from './components'
import {PT_Profile} from './components'
import {Patients} from './components'
import {Patient_Profile} from './components'
import {Treatment_Fee} from './components'
import {ChangePassword} from './components'

// Good
import { 
  Login,
  ForgotPassword,
  PT_Profile,
  Patients,
  Patient_Profile,
  Treatment_Fee,
  ChangePassword
} from './components'
```

#### อย่าเหนื่อยพิมสองรอบเลย
```jsx
// Bad
const data = {
    UserReducer : UserReducer,
    PTReducer : PTReducer,
    ConfigReducer : ConfigReducer,
    PatientReducer : PatientReducer,
    AssessmentReducer :AssessmentReducer,
    AlertReducer:AlertReducer,
    As_BackReducer :As_BackReducer,
    As_ShoulderReducer :As_ShoulderReducer,
    SOAPReducer : SOAPReducer,
}

// Good
const data = {
    UserReducer,
    PTReducer,
    ConfigReducer,
    PatientReducer,
    AssessmentReducer,
    AlertReducer,
    As_BackReducer,
    As_ShoulderReducer,
    SOAPReducer,
}
```

#### ไม่เบื่อบ้างหรือ
```jsx
// Bad
day_th(value){
  let result
  if(value ==="Sunday"){
    result = 'อาทิตย์'
  }else if(value ==="Monday"){
    result = 'จันทร์'
  }else if(value ==="Tuesday"){
    result = 'อังคาร'
  }else if(value ==="Wednesday"){
    result = 'พุธ'
  }else if(value ==="Thursday"){
    result = 'พฤหัสบดี'
  }else if(value ==="Friday"){
    result = 'ศุกร์'
  }else if(value ==="Saturday"){
    result = 'เสาร์'
  }
  return result
}

// Good
day_th(day_en){
  const dayOfweek = [
    { th: "อาทิตย์",   en: "Sunday" },
    { th: "จันทร์",    en: "Monday" },
    { th: "อังคาร",   en: "Tuesday" },
    { th: "พุธ",     en: "Wednesday" },
    { th: "พฤหัสบดี", en: "Thursday" },
    { th: "ศุกร์",    en: "Friday" },
    { th: "เสาร์",    en: "Saturday" }
  ]
  let day = dayOfweek.find((day)=> day.en === day_en);
  return day.th;
}
```
