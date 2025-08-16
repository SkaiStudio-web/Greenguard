# Greenguard
Computer Science Education Project – GreenGuard: A web application designed to educate and raise awareness about environmental hazard prevention.
greenguard/
 ├── package.json
  ├── public/
   │    └── index.html
    │    └── logo.png
     └── src/
           ├── index.js
                 └── App.jsx{
                      "name": "greenguard",
                        "version": "1.0.0",
                          "private": true,
                            "dependencies": {
                                "framer-motion": "^10.16.4",
                                    "lucide-react": "^0.284.0",
                                        "recharts": "^2.9.0",
                                            "react": "^18.2.0",
                                                "react-dom": "^18.2.0",
                                                    "react-scripts": "5.0.1"
                                                      },
                                                        "scripts": {
                                                            "start": "react-scripts start",
                                                                "build": "react-scripts build",
                                                                    "test": "react-scripts test",
                                                                        "eject": "react-scripts eject"
                                                                          }
                                                                          }
                 }
                 <!DOCTYPE html>
                 <html lang="en">
                   <head>
                       <meta charset="utf-8" />
                           <meta name="viewport" content="width=device-width, initial-scale=1" />
                               <title>Computer Science Education Project</title>
                                 </head>
                                   <body>
                                       <div id="root"></div>
                                         </body>
                                         </html>import React from 'react';
                                         import ReactDOM from 'react-dom/client';
                                         import App from './App';

                                         const root = ReactDOM.createRoot(document.getElementById('root'));
                                         root.render(
                                           <React.StrictMode>
                                               <App />
                                                 </React.StrictMode>
                                                 );import React, { useState, useEffect } from "react";
                                                 import { LineChart, Line, XAxis, YAxis, Tooltip, CartesianGrid } from "recharts";

                                                 const tips = [
                                                   "Turn off lights when not in use.",
                                                     "Use a reusable water bottle.",
                                                       "Plant a tree or care for a plant.",
                                                         "Dispose of waste properly.",
                                                           "Save water by fixing leaks."
                                                           ];

                                                           export default function App() {
                                                             const [dailyTip, setDailyTip] = useState("");

                                                               useEffect(() => {
                                                                   setDailyTip(tips[Math.floor(Math.random() * tips.length)]);
                                                                     }, []);

                                                                       return (
                                                                           <div className="min-h-screen bg-gray-50 text-gray-900 p-4">
                                                                                 <header className="text-center mb-6">
                                                                                         <img src="/logo.png" alt="Logo" className="mx-auto w-20 h-20 mb-2" />
                                                                                                 <h1 className="text-2xl font-bold">Computer Science Education Project</h1>
                                                                                                         <h2 className="text-lg text-green-700">
                                                                                                                   GreenGuard – Environmental Hazard Awareness & Prevention
                                                                                                                           </h2>
                                                                                                                                 </header>

                                                                                                                                       <div className="bg-white rounded-xl shadow p-4 mb-6 text-center">
                                                                                                                                               <h3 className="font-semibold mb-2">🌱 Daily Eco Tip</h3>
                                                                                                                                                       <p>{dailyTip}</p>
                                                                                                                                                             </div>

                                                                                                                                                                   <div className="bg-white rounded-xl shadow p-4">
                                                                                                                                                                           <h3 className="font-semibold mb-2">📊 Weekly Impact Tracker</h3>
                                                                                                                                                                                   <LineChart
                                                                                                                                                                                             width={300}
                                                                                                                                                                                                       height={200}
                                                                                                                                                                                                                 data={[
                                                                                                                                                                                                                             { day: "Mon", impact: 2 },
                                                                                                                                                                                                                                         { day: "Tue", impact: 3 },
                                                                                                                                                                                                                                                     { day: "Wed", impact: 1 },
                                                                                                                                                                                                                                                                 { day: "Thu", impact: 4 },
                                                                                                                                                                                                                                                                             { day: "Fri", impact: 2 },
                                                                                                                                                                                                                                                                                         { day: "Sat", impact: 5 },
                                                                                                                                                                                                                                                                                                     { day: "Sun", impact: 3 }
                                                                                                                                                                                                                                                                                                               ]}
                                                                                                                                                                                                                                                                                                                       >
                                                                                                                                                                                                                                                                                                                                 <CartesianGrid strokeDasharray="3 3" />
                                                                                                                                                                                                                                                                                                                                           <XAxis dataKey="day" />
                                                                                                                                                                                                                                                                                                                                                     <YAxis />
                                                                                                                                                                                                                                                                                                                                                               <Tooltip />
                                                                                                                                                                                                                                                                                                                                                                         <Line type="monotone" dataKey="impact" stroke="#82ca9d" />
                                                                                                                                                                                                                                                                                                                                                                                 </LineChart>
                                                                                                                                                                                                                                                                                                                                                                                       </div>
                                                                                                                                                                                                                                                                                                                                                                                           </div>
                                                                                                                                                                                                                                                                                                                                                                                             );
                                                                                                                                                                                                                                                                                                                                                                                             }