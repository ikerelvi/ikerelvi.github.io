---
layout: page
title: Contact
permalink: /contact/
---

If you’d like to collaborate or discuss opportunities, send me a message here.

<form id="contactForm" class="contact-form" data-endpoint="{{ site.endpoint }}">
  <div class="form-row">
    <label for="name">Name</label>
    <input id="name" name="name" type="text" autocomplete="name" required>
  </div>

  <div class="form-row">
    <label for="email">Email</label>
    <input id="email" name="email" type="email" autocomplete="email" required>
  </div>

  <div class="form-row">
    <label for="subject">Subject</label>
    <input id="subject" name="subject" type="text" placeholder="Project / enquiry">
  </div>

  <div class="form-row">
    <label for="message">Message</label>
    <textarea id="message" name="message" rows="6" required></textarea>
  </div>

  <input type="hidden" name="page" value="/contact/">

  <!-- Honeypot -->
  <div class="hp-field" aria-hidden="true">
    <label for="website">Website</label>
    <input id="website" name="website" type="text" tabindex="-1" autocomplete="off">
  </div>

  <button class="btn primary" type="submit">Send message</button>

  <p id="formStatus" class="muted" style="margin:12px 0 0;"></p>
</form>

<!--p class="muted" style="margin-top:14px;">
Prefer email? <a href="mailto:{{ site.email }}">{{ site.email }}</a>
</p-->
<p class="muted" style="margin-top:14px;">
</p>
<script>
  (function () {
    const form = document.getElementById("contactForm");
    const statusEl = document.getElementById("formStatus");
    const endpoint = form.getAttribute("data-endpoint");

    function setStatus(msg) {
      statusEl.textContent = msg || "";
    }

    form.addEventListener("submit", async (e) => {
      e.preventDefault();
      setStatus("");

      const submitBtn = form.querySelector('button[type="submit"]');
      submitBtn.disabled = true;
      submitBtn.style.opacity = "0.7";
      setStatus("Sending…");

      try {
        // Build x-www-form-urlencoded body
        const formData = new FormData(form);
        const params = new URLSearchParams();
        for (const [k, v] of formData.entries()) params.append(k, v);

        const res = await fetch(endpoint, {
          method: "POST",
          headers: { "Content-Type": "application/x-www-form-urlencoded;charset=UTF-8" },
          body: params.toString(),
        });

        if (!res.ok) throw new Error("Request failed");

        // Optional: if your script returns JSON, you can read it:
        // const data = await res.json();

        window.location.href = "/thanks/";
      } catch (err) {
        console.error(err);
        setStatus("Something went wrong. Please try again or email me directly.");
        submitBtn.disabled = false;
        submitBtn.textContent = "Send message";
        submitBtn.style.opacity = "1";
      }
    });
  })();
</script>
