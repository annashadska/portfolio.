const menuToggle = document.getElementById("menuToggle");
const mainNav = document.getElementById("mainNav");

// Мобільне меню
menuToggle.addEventListener("click", () => {
  const isOpen = mainNav.classList.toggle("open");

  menuToggle.setAttribute("aria-expanded", String(isOpen));
  menuToggle.textContent = isOpen ? "✕" : "☰";
});

// Закриваємо меню після натискання на пункт
mainNav.querySelectorAll("a").forEach(link => {
  link.addEventListener("click", () => {
    mainNav.classList.remove("open");
    menuToggle.setAttribute("aria-expanded", "false");
    menuToggle.textContent = "☰";
  });
});

// Вибір послуги
const serviceLinks = document.querySelectorAll("[data-service]");
const contactCopy = document.querySelector(".contact-copy");

serviceLinks.forEach(link => {
  link.addEventListener("click", () => {
    const service = link.dataset.service;

    if (contactCopy && service) {
      contactCopy.textContent =
        `Вас цікавить «${service}». Напишіть мені в Instagram — обговоримо деталі.`;
    }
  });
});

// Плавна поява блоків під час прокручування
const revealElements = document.querySelectorAll(
  ".service-card, .strategy-card, .portfolio-feature, .inside-grid > div, .process-steps article, .about-main"
);

revealElements.forEach(element => {
  element.classList.add("reveal");
});

if ("IntersectionObserver" in window) {
  const observer = new IntersectionObserver(
    (entries, currentObserver) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add("visible");
          currentObserver.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.12 }
  );

  revealElements.forEach(element => {
    observer.observe(element);
  });
} else {
  revealElements.forEach(element => {
    element.classList.add("visible");
  });
}
