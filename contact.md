---
layout: default
is_contact: true
title: Contact
---

<style>
  .contact-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
  }

  .contact-heading {
    font-size: 2em;
    margin-bottom: 30px;
    text-align: center;
    color: #333;
  }

  .contact-links {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin-bottom: 40px;
    width: 100%;
  }

  .contact-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-decoration: none;
    color: #333;
    transition: transform 0.3s ease, color 0.3s ease;
    width: 100px;
  }

  .contact-link:hover {
    transform: translateY(-5px);
    color: #FF0F00;
    text-decoration: none;
  }

  .contact-icon {
    font-size: 2.5em;
    margin-bottom: 10px;
  }

  .contact-label {
    font-size: 0.9em;
    text-align: center;
  }

  .contact-email {
    display: flex;
    align-items: center;
    margin-top: 20px;
    padding: 15px;
    background-color: #f8f8f8;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
  }

  .contact-email:hover {
    transform: translateY(-3px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.15);
  }

  .email-icon {
    font-size: 1.5em;
    margin-right: 15px;
    color: #FF0F00;
  }

  .email-address {
    font-size: 1.1em;
  }

  .email-domain {
    font-size: 1.1em;
  }

  @media (max-width: 600px) {
    .contact-links {
      gap: 15px;
    }
    
    .contact-link {
      width: 80px;
    }
    
    .contact-icon {
      font-size: 2em;
    }
  }
</style>

<!-- Font Awesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" integrity="sha512-iecdLmaskl7CVkqkXNQ/ZH/XLlvWZOJyj7Yy7tcenmpD1ypASozpmT/E0iPtmFIB46ZmdtAc9eNBvH0H/ZpiBw==" crossorigin="anonymous" referrerpolicy="no-referrer" />

<div class="contact-container">
  <h1 class="contact-heading">Connect With Me</h1>
  
  <div class="contact-links">
    <a href="https://twitter.com/abogadoron" class="contact-link" aria-label="Twitter">
      <i class="fa-brands fa-twitter contact-icon" aria-hidden="true"></i>
      <span class="contact-label">Twitter/X</span>
    </a>
    <a href="https://linkedin.com/in/hirotake-ito-038053140/" class="contact-link" aria-label="LinkedIn">
      <i class="fa-brands fa-linkedin contact-icon" aria-hidden="true"></i>
      <span class="contact-label">LinkedIn</span>
    </a>
    <a href="https://github.com/HirotakeIto" class="contact-link" aria-label="GitHub">
      <i class="fa-brands fa-github contact-icon" aria-hidden="true"></i>
      <span class="contact-label">GitHub</span>
    </a>
  </div>
  
  <a class="contact-email" aria-label="Email me">
    <i class="fa-solid fa-envelope email-icon" aria-hidden="true"></i>
    <span class="email-address">itouhrtk</span>
  </a>
</div>

<script>
  // スパムボット対策のためにJavaScriptでメールアドレスを隠す
  document.addEventListener('DOMContentLoaded', function() {
    const emailSpan = document.querySelector('.email-address');
    
    // メールアドレスをクリックした時のイベント
    document.querySelector('.contact-email').addEventListener('click', function() {
      const email = emailSpan.textContent + '@gmail.com';
      navigator.clipboard.writeText(email).then(() => {
        alert('メールアドレスがクリップボードにコピーされました');
      });
    });
  });
</script>
