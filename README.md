var your_css_above = `
/* Card Centering */
.create-container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 70vh;
}
.create-card {
    background: #fff;
    padding: 2.5rem 2rem 1.5rem 2rem;
    border-radius: 14px;
    box-shadow: 0 6px 32px rgba(80,80,120,0.1), 0 1.5px 6px rgba(50,50,50,0.08);
    max-width: 420px;
    width: 100%;
}
.create-card h3 {
    text-align: center;
    margin-bottom: 1.5rem;
    font-weight: 700;
    font-size: 1.45em;
    color: #20135d;
    letter-spacing: 0.9px;
}
.form-label {
    font-weight: 500;
    margin-bottom: 0.3rem;
    color: #232355;
    display: block;
}
/* ...copy rest of your CSS here... */
`;

var html = `
<div class="create-container">
  <div class="create-card">
    <!-- Your form fields here -->
  </div>
</div>
`;

$('.workarea').html('<style>' + your_css_above + '</style>' + html);
