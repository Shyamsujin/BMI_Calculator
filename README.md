# Ex:06 BMI Calculator
## Date:29.10.25
### Name : SHYAM SUJIN U
### Reg no: 212223040201

## AIM:
To create a BMI calculator using React Router 

## ALGORITHM:
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM:

### APP.jsx
```
import React, { useState } from 'react';
import './App.css';

function App() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState('');

  const calculateBMI = (e) => {
    e.preventDefault();

    if (!weight || !height) {
      alert('Please enter both weight and height.');
      return;
    }

    const heightInMeters = height / 100;
    const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(2);

    setBmi(bmiValue);

    if (bmiValue < 18.5) setMessage('Underweight');
    else if (bmiValue >= 18.5 && bmiValue < 24.9) setMessage('Normal weight');
    else if (bmiValue >= 25 && bmiValue < 29.9) setMessage('Overweight');
    else setMessage('Obese');
  };

  return (
    <div className="bmi-container">
      <h1>BMI Calculator</h1>
      <form onSubmit={calculateBMI}>
        <input
          type="number"
          placeholder="Weight (kg)"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
        <input
          type="number"
          placeholder="Height (cm)"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
        <button type="submit">Calculate</button>
      </form>

      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p>Status: {message}</p>
        </div>
      )}
    </div>
  );
}
export default App;
```
## App.css
```
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
  font-family: Arial, sans-serif;
}

.bmi-container {
  display: flex;
  flex-direction: column;
  justify-content: center;   
  align-items: center;       
  height: 100vh;             
  width: 100vw;              
  background: linear-gradient(135deg, #89f7fe, #66a6ff); 
  text-align: center;
}

.bmi-container h1 {
  color: #003c8f;
  font-size: 2.5rem;
  margin-bottom: 30px;
}

form {
  background: rgba(255, 255, 255, 0.9);
  padding: 30px 40px;
  border-radius: 20px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}

input {
  padding: 12px;
  width: 240px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 10px;
  outline: none;
  text-align: center;
}

button {
  padding: 12px 24px;
  font-size: 16px;
  background-color: #0077ff;
  color: white;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background-color: #005fcc;
}

.result {
  margin-top: 30px;
  font-size: 22px;
  color: #003c8f;
}

```
## output:
<img width="1920" height="1080" alt="Screenshot (44)" src="https://github.com/user-attachments/assets/98e95743-9fff-4af3-bb5a-a6773c222541" />


## Result:
The program for creating BMI Calculator using React Router is executed successfully.
