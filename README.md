// Place this inside your createNotification function in notificationsRouter.js

var your_css_above = `
.create-container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 90vh;
    background: #fafbff;
}
.create-card {
    background: #fff;
    padding: 2.5rem 2.5rem 2rem 2.5rem;
    border-radius: 18px;
    box-shadow: 0 8px 32px rgba(80, 120, 210, 0.09), 0 1.5px 6px rgba(50, 50, 90, 0.08);
    max-width: 520px;
    width: 100%;
    margin: 3rem 0;
}
.create-card h3 {
    text-align: center;
    margin-bottom: 2.2rem;
    font-weight: 700;
    font-size: 2rem;
    color: #223359;
    letter-spacing: 0.7px;
}
.form-label {
    font-weight: 600;
    margin-bottom: 0.6rem;
    margin-top: 1rem;
    color: #203040;
    font-size: 1.08rem;
    display: block;
    letter-spacing: 0.1em;
}
.form-control, .form-select {
    width: 100%;
    padding: 1.1rem 1.2rem;
    margin-bottom: 0.7rem;
    font-size: 1.08rem;
    border: 1px solid #d2d6dc;
    border-radius: 9px;
    background: #f6f8fb;
    transition: border 0.2s;
    min-height: 54px;
}
.form-control:focus, .form-select:focus {
    outline: none;
    border-color: #4a77ff;
    background: #f1f5fe;
}
textarea.form-control {
    min-height: 90px;
    max-height: 160px;
    resize: vertical;
}
.btn-primary {
    display: block;
    width: 100%;
    padding: 1.08rem 0;
    background: linear-gradient(90deg, #306BFF 70%, #0A4BFF 100%);
    border: none;
    color: #fff;
    font-size: 1.18rem;
    border-radius: 9px;
    font-weight: 600;
    margin-top: 1.6rem;
    box-shadow: 0 2px 12px 0 rgba(40,90,200,0.08);
    transition: background 0.2s;
    letter-spacing: 0.09em;
}
.btn-primary:hover {
    background: linear-gradient(90deg, #0A4BFF 90%, #306BFF 100%);
}
`;

var html = `
<div class="create-container">
  <div class="create-card">
    <h3>Create Notification</h3>
    <form>
      <label class="form-label" for="message">Message</label>
      <textarea class="form-control" id="message" placehold
