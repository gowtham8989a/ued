EXP2---WEBSITE

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Online Store Checkout</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #f9f9f9;
    }
    header {
      background: #0077cc;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    .container {
      max-width: 800px;
      margin: 2rem auto;
      background: white;
      padding: 2rem;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }
    h2 {
      margin-top: 0;
    }
    label {
      display: block;
      margin: 1rem 0 0.5rem;
    }
    input,
    select {
      width: 100%;
      padding: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      background: #0077cc;
      color: white;
      padding: 0.75rem 1.5rem;
      border: none;
      border-radius: 4px;
      margin-top: 1.5rem;
      cursor: pointer;
    }
    button:hover {
      background: #005fa3;
    }
    .confirmation {
      display: none;
      color: green;
      margin-top: 1rem;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <header>
    <h1>Online Store Checkout</h1>
  </header>

  <div class="container">
    <h2>Shipping Information</h2>
    <form id="checkout-form">
      <label for="name">Full Name</label>
      <input type="text" id="name" required />

      <label for="address">Address</label>
      <input type="text" id="address" required />

      <label for="email">Email</label>
      <input type="email" id="email" required />

      <label for="shipping">Shipping Method</label>
      <select id="shipping">
        <option value="standard">Standard (Free)</option>
        <option value="express">Express (+₹50)</option>
      </select>

      <label for="payment">Payment Method</label>
      <select id="payment">
        <option value="card">Credit/Debit Card</option>
        <option value="upi">UPI / Wallet</option>
        <option value="cod">Cash on Delivery</option>
      </select>

      <button type="submit">Place Order Securely</button>
      <div class="confirmation" id="confirmation">
        ✅ Order placed successfully!
      </div>
    </form>
  </div>

  <script>
    document.getElementById('checkout-form').addEventListener('submit', function (e) {
      e.preventDefault();
      document.getElementById('confirmation').style.display = 'block';
    });
  </script>
</body>
</html>


------------------------------------------------------


EXP3----------CHAT APP

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Simple Chat Module</title>
    <!-- <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f1f1f1;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .chat-container {
            width: 350px;
            height: 500px;
            background: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            display: flex;
            flex-direction: column;
            border-radius: 10px;
            overflow: hidden;
        }

        .chat-header {
            background-color: #007bff;
            color: white;
            padding: 10px;
            text-align: center;
            font-weight: bold;
        }

        .chat-messages {
            flex: 1;
            padding: 10px;
            overflow-y: auto;
            background-color: #f9f9f9;
        }

        .message {
            margin: 8px 0;
            max-width: 70%;
            padding: 10px;
            border-radius: 10px;
            clear: both;
            word-wrap: break-word;
        }

        .user-message {
            background-color: #dcf8c6;
            float: right;
            text-align: right;
        }

        .bot-message {
            background-color: #ececec;
            float: left;
            text-align: left;
        }

        .chat-input {
            display: flex;
            border-top: 1px solid #ccc;
        }

        .chat-input input {
            flex: 1;
            padding: 10px;
            border: none;
            outline: none;
        }

        .chat-input button {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
        }

        .chat-input button:hover {
            background-color: #0056b3;
        }
    </style> -->
</head>

<body>

    <div class="chat-container">
        <div class="chat-header">Chat Module</div>
        <div class="chat-messages" id="chatMessages"></div>
        <div class="chat-input">
            <input type="text" id="chatInput" placeholder="Type a message..." />
            <button onclick="sendMessage()">Send</button>
        </div>
    </div>

    <script>
        function sendMessage() {
            const input = document.getElementById('chatInput');
            const msg = input.value.trim();
            if (msg === '') return;

            addMessage(msg, 'user');

            // Simulated bot reply
            setTimeout(() => {
                addMessage("You said: " + msg, 'bot');
            }, 500);

            input.value = '';
        }

        function addMessage(text, type) {
            const chat = document.getElementById('chatMessages');
            const msgDiv = document.createElement('div');
            msgDiv.classList.add('message');
            msgDiv.classList.add(type === 'user' ? 'user-message' : 'bot-message');
            msgDiv.innerText = text;
            chat.appendChild(msgDiv);
            chat.scrollTop = chat.scrollHeight;
        }
    </script>

</body>

</html>
------------------------------------------------------

EXP4 --------- CALCI  
create a folder and open in React
IN CMD PRMPT 
npx create-react-app calci
cd calci
npm start
directly paste this into app.js

import React, { useState } from "react";

function App() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const handleClear = () => {
    setInput("");
  };

  const handleEquals = () => {
    try {
      // eslint-disable-next-line no-eval
      setInput(eval(input).toString());
    } catch (error) {
      setInput("Error");
    }
  };

  return (
    <div style={styles.container}>
      <h2>React Calculator</h2>
      <input style={styles.input} type="text" value={input} readOnly />
      <div style={styles.buttonGrid}>
        {["7", "8", "9", "/", "4", "5", "6", "*", "1", "2", "3", "-", "0", ".", "=", "+"].map(
          (val) => (
            <button
              key={val}
              style={styles.button}
              onClick={() => (val === "=" ? handleEquals() : handleClick(val))}
            >
              {val}
            </button>
          )
        )}
        <button style={styles.clearButton} onClick={handleClear}>
          C
        </button>
      </div>
    </div>
  );
}

const styles = {
  container: {
    width: "250px",
    margin: "50px auto",
    padding: "20px",
    border: "2px solid #ccc",
    borderRadius: "10px",
    textAlign: "center",
    backgroundColor: "#f9f9f9",
  },
  input: {
    width: "100%",
    height: "40px",
    fontSize: "18px",
    marginBottom: "10px",
    textAlign: "right",
    padding: "5px",
  },
  buttonGrid: {
    display: "grid",
    gridTemplateColumns: "repeat(4, 1fr)",
    gap: "10px",
  },
  button: {
    padding: "15px",
    fontSize: "18px",
    borderRadius: "5px",
    backgroundColor: "#eee",
    border: "1px solid #ccc",
    cursor: "pointer",
  },
  clearButton: {
    gridColumn: "span 4",
    padding: "10px",
    fontSize: "18px",
    backgroundColor: "#ff9999",
    border: "none",
    borderRadius: "5px",
    cursor: "pointer",
  },
};

export default App;

----------------------------------------------------------
EXP5 ----- VOTING App REACT 
import React, { useState } from "react";

function App() {
  const [candidates, setCandidates] = useState([
    { name: "Alice", votes: 0 },
    { name: "Bob", votes: 0 },
    { name: "Charlie", votes: 0 },
  ]);

  const handleVote = (index) => {
    const updated = candidates.map((c, i) =>
      i === index ? { ...c, votes: c.votes + 1 } : c
    );
    setCandidates(updated);
  };

  return (
    <div style={{ textAlign: "center", marginTop: "50px" }}>
      <h2>Simple Voting App 🗳️</h2>
      {candidates.map((c, i) => (
        <div key={i} style={{ margin: "10px" }}>
          <p>
            {c.name}: {c.votes} votes
          </p>
          <button onClick={() => handleVote(i)}>Vote</button>
        </div>
      ))}
    </div>
  );
}

export default App;

----------------------------------------------------------
EXP6  LEAP html
<!DOCTYPE html>
<html>
<head>
  <title>Leap Year Checker</title>
</head>
<body>
  <script>
    function checkLeapYear() {
      let yearInput = prompt("Enter a year:");
      let year = parseInt(yearInput);
      if (isNaN(year)) {
        alert("Invalid input. Please enter a valid year (a number).");
        return;
      }
      let isLeap = (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0);
      if (isLeap) {
        alert(year + " is a leap year.");
      } else {
        alert(year + " is not a leap year.");
      }
    }
    checkLeapYear();
  </script>
</body>
</html>
----------------------------------------------------------
EXP7 BIRTHDAY REMINDER
import React, { useState } from "react";

function App() {
  const [name, setName] = useState("");
  const [date, setDate] = useState("");
  const [birthdays, setBirthdays] = useState([]);

  const addBirthday = () => {
    if (name && date) {
      setBirthdays([...birthdays, { name, date }]);
      setName("");
      setDate("");
    }
  };

  return (
    <div style={{ textAlign: "center", marginTop: "50px" }}>
      <h2>🎂 Birthday Reminder</h2>

      <input
        type="text"
        placeholder="Enter name"
        value={name}
        onChange={(e) => setName(e.target.value)}
      />
      <br /><br />

      <input
        type="date"
        value={date}
        onChange={(e) => setDate(e.target.value)}
      />
      <br /><br />

      <button onClick={addBirthday}>Add Reminder</button>

      <h3 style={{ marginTop: "30px" }}>Upcoming Birthdays</h3>
      <ul style={{ listStyle: "none", padding: 0 }}>
        {birthdays.map((b, i) => (
          <li key={i}>
            {b.name} — {b.date}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;

