import React, { useState } from "react";

function App() {
  const [task, setTask] = useState("");
  const [message, setMessage] = useState("");

  const addTask = async () => {
    const res = await fetch(https://dpc1ccf9hc.execute-api.us-east-1.amazonaws.com, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({ id: Date.now().toString(), task })
    });
    const data = await res.json();
    setMessage(data.message);
  };

  return (
    <div>
      <h1>Serverless To-Do List</h1>
      <input value={task} onChange={(e) => setTask(e.target.value)} />
      <button onClick={addTask}>Add Task</button>
      {message && <p>{message}</p>}
    </div>
  );
}

export default App;


