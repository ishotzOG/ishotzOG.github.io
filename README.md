<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Admin Portal | Private</title>
  <style>
    body {
      /* Sky Blue background */
      background-color: #87CEEB; 
      color: #1a202c;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
    }
    .dashboard {
      background-color: white;
      padding: 40px;
      border-radius: 12px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
      text-align: center;
      max-width: 500px;
      width: 90%;
      /* Golden border */
      border: 4px solid #FFD700; 
    }
    h1 {
      /* Golden text with a slight dark outline for readability */
      color: #DAA520; 
      margin-top: 0;
      font-size: 2.2em;
      text-transform: uppercase;
      letter-spacing: 2px;
    }
    p {
      color: #4a5568;
      margin-bottom: 30px;
      font-weight: 500;
    }
    .secure-btn {
      display: block;
      width: 100%;
      padding: 15px 0;
      margin-bottom: 15px;
      /* Golden button */
      background-color: #FFD700; 
      color: #000;
      text-decoration: none;
      font-weight: bold;
      font-size: 1.1em;
      border-radius: 8px;
      border: 2px solid #DAA520;
      transition: background-color 0.3s;
    }
    .secure-btn:hover {
      background-color: #FFC125;
    }
    .warning {
      font-size: 0.85em;
      color: #e53e3e;
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <div class="dashboard">
    <h1>Admin Vault</h1>
    <p>Secure Personal Document Portal</p>

    <!-- Replace the 'https://drive.google.com/file/d/1Vm7Z58_8EDALPJKcEgPl7iAgcK6AyRve/view?usp=drive_link' with your actual Google Drive folder links -->
    <a href="https://drive.google.com/file/d/1Vm7Z58_8EDALPJKcEgPl7iAgcK6AyRve/view?usp=drive_link" class="secure-btn" target="_blank">Access Tax & ID Documents</a>
    <a href="https://drive.google.com/file/d/1Vm7Z58_8EDALPJKcEgPl7iAgcK6AyRve/view?usp=drive_link" class="secure-btn" target="_blank">Access College Records</a>
    
    <div class="warning">
      🔒 Restricted Access. Authentication required by hosting provider.
    </div>
  </div>

</body>
</html>
