import React, { useEffect, useState } from "react";

function App() {
  const [scores, setScores] = useState([]);
  const ws = new WebSocket("YOUR_WEBSOCKET_URL");

  useEffect(() => {
    ws.onmessage = (event) => {
      setScores(JSON.parse(event.data));
    };
  }, []);

  return (
    <div>
      <h1>Live Scores</h1>
      {scores.map((match) => (
        <p key={match.match_id}>{match.score}</p>
      ))}
    </div>
  );
}

export default App;



