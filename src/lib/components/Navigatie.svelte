<script>
import bookImage from '$lib/assets/boek-image.png'
    import { onMount } from "svelte";

    let darkMode = false;

    onMount(() => {
        const body = document.querySelector("body");
        const sidebar = body.querySelector("nav");
        const toggle = document.querySelector(".toggle");
        const searchBtn = document.querySelector(".search-box input");
        const modeSwitch = document.querySelector(".toggle-switch");
        const modeText = document.querySelector(".mode-text");

        toggle.addEventListener("click", () => {
            sidebar.classList.toggle("close");
        });

        searchBtn.addEventListener("focus", () => {
            sidebar.classList.remove("close");
        });

        modeSwitch.addEventListener("click", () => {
            body.classList.toggle("dark");
            darkMode = !darkMode;

            if (darkMode) {
                modeText.innerText = "Light Mode";
            } else {
                modeText.innerText = "Dark Mode";
            }
        });
    });
</script>
    <nav>
        <header>
            <section>
                <span>
                    <img src="{bookImage}" alt="Gebruiker-foto">
                </span>

                <div>
                    <span>User Name</span>
                    <span>5 jaar lid</span>
                </div>
            </section>

            <i class='bx bx-chevron-right toggle' title="#todo"></i>
        </header>

        <section>
            <section>
                <li>
                    <i class='bx bx-search icon'  title="#todo"></i>
                    <input type="text" placeholder="Zoek...">
                </li>

                <ul>
                    <li class="nav-link">
                        <a href="/">
                            <i class='bx bx-home icon'  title="#todo"></i>
                            <span class="text nav-text">Welkom</span>
                        </a>
                    </li>

                    <li class="nav-link">
                        <a href="/leeslijst">
                            <i class='bx bx-list-ul icon'  title="#todo"></i>
                            <span class="text nav-text">Leeslijst</span>
                        </a>
                    </li>

                    <li class="nav-link">
                        <a href="/uitleningen-en-verlengen">
                            <i class='bx bx-bar-chart-alt-2 icon'  title="#todo"></i>
                            <span class="text-long nav-text">Uitleningen en verlengen</span>
                        </a>
                    </li>

                    <li class="nav-link">
                        <a href="/Uitleengeschiedenis">
                            <i class='bx bx-bell icon'  title="#todo"></i>
                            <span class="text nav-text">Uitleengeschiedenis</span>
                        </a>
                    </li>

                    <li class="nav-link">
                        <a href="/Betaalgeschiedenis">
                            <i class='bx bx-pie-chart-alt icon' title="#todo" ></i>
                            <span class="text nav-text">Betaalgeschiedenis</span>
                        </a>
                    </li>

                    <li class="nav-link">
                        <a href="/Reserveringen">
                            <i class='bx bx-heart icon' title="#todo"></i>
                            <span class="text nav-text">Reserveringen</span>
                        </a>
                    </li>

                    <li class="nav-link">
                        <a href="/desposito's">
                            <i class='bx bx-wallet icon' title="#todo"></i>
                            <span class="text nav-text">Desposito's</span>
                        </a>
                    </li>

                    <li class="nav-link">
                        <a href="/tellerstand-abonnement">
                            <i class='bx bx-wallet icon'  title="#todo"></i>
                            <span class="text nav-text">Tellerstand abonnement</span>
                        </a>
                    </li>
                </ul>
            </section>

            <section>
                <ul>
                <li>
                    <a href="/uitloggen">
                        <i class='bx bx-log-out icon' title="#todo"></i>
                        <span>Uitloggen</span>
                    </a>
                </li>

                <li class="mode">
                    <div class="sun-moon">
                        <i class='bx bx-moon icon moon' title="#todo"></i>
                        <i class='bx bx-sun icon sun' title="#todo"></i>
                    </div>
                    <span class="mode-text text">Dark mode</span>

                    <div class="toggle-switch">
                        <span class="switch"></span>
                    </div>
                </li>
            </ul>
            </section>
        </section>
    </nav>
    <style>
        :root {
            --primary-red: #FF2E17;
            --primary-white: #ffff;
            --primary-black: #0000;
            --primary-grey: #9B9C9F;
        }
        body {
            overflow-x: hidden !important;
            background-color: #E3E9F9;
            margin: 0;
            padding: 0;
        }

        nav {
            position: fixed;
            top: 0;
            left: 0;
            height: 100%;
            width: 250px;
            padding: 10px 14px;
            background: var(--primary-white);
            z-index: 100;
        }

        nav header {
            position: relative;
        }

        nav header > section {
            display: flex;
            align-items: center;
        }

        nav header img {
            width: 3rem;
            height: 3rem;
            border-radius: 180px;
        }

        nav header .toggle {
            position: absolute;
            top: 50%;
            right: -25px;
            transform: translateY(-50%) rotate(180deg);
            height: 25px;
            width: 25px;
            background-color: var(--primary-red);
            color: var(--primary-black);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
    </style>