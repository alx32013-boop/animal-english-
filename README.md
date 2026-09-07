<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Animal Cards</title>

    <link
        rel="stylesheet"
        href="style.css"
    >
</head>

<body>

    <div class="app">

        <!-- =========================
             PANEL LATERAL
        ========================== -->

        <aside class="sidebar">

            <div class="logo">

                <div class="logo-icon">
                    🐾
                </div>

                <h1>
                    ANIMAL<br>
                    CARDS
                </h1>

            </div>


            <div class="sidebar-line"></div>


            <div class="code-section">

                <h2>
                    ENTER CODE
                </h2>

                <p>
                    Find secret codes and unlock new animal cards!
                </p>


                <div class="input-container">

                    <input
                        type="text"
                        id="codeInput"
                        placeholder="Enter code..."
                        autocomplete="off"
                    >

                    <button
                        id="unlockButton"
                    >
                        UNLOCK
                    </button>

                </div>


                <div
                    id="message"
                    class="message"
                >
                    Enter a code to begin!
                </div>

            </div>


            <div class="collection-info">

                <span>
                    COLLECTION
                </span>

                <strong id="cardCounter">
                    0 / 1
                </strong>

            </div>


            <div class="progress-container">

                <div
                    id="progressBar"
                    class="progress-bar"
                ></div>

            </div>


            <div class="instructions">

                <h3>
                    HOW TO PLAY
                </h3>

                <ol>
                    <li>Find a secret code.</li>
                    <li>Enter the code.</li>
                    <li>Unlock the animal.</li>
                    <li>Collect them all!</li>
                </ol>

            </div>

        </aside>


        <!-- =========================
             CONTENIDO PRINCIPAL
        ========================== -->

        <main class="main-content">


            <header class="top-bar">

                <div>

                    <h2>
                        MY COLLECTION
                    </h2>

                    <p>
                        Discover and collect amazing animals
                    </p>

                </div>


                <div class="cards-number">

                    <span>
                        CARDS
                    </span>

                    <strong id="topCounter">
                        0
                    </strong>

                </div>

            </header>


            <!-- =========================
                 ZONA DE CARTAS
            ========================== -->

            <section class="cards-area">


                <button
                    class="arrow arrow-left"
                    id="previousButton"
                    aria-label="Previous card"
                >
                    ❮
                </button>


                <div class="card-display">

                    <div
                        id="emptyState"
                        class="empty-state"
                    >

                        <div class="empty-icon">
                            🃏
                        </div>

                        <h2>
                            NO CARDS YET
                        </h2>

                        <p>
                            Enter a secret code to unlock your first animal!
                        </p>

                    </div>


                    <div
                        id="animalCard"
                        class="animal-card hidden"
                    >

                        <div class="card-top">

                            <span class="rarity">
                                COMMON
                            </span>

                            <span class="card-number">
                                #001
                            </span>

                        </div>


                        <div
                            id="animalEmoji"
                            class="animal-image"
                        >
                            🦁
                        </div>


                        <div class="card-info">

                            <h1 id="animalName">
                                LION
                            </h1>

                            <p id="animalType">
                                WILD ANIMAL
                            </p>


                            <div class="stats">

                                <div class="stat">

                                    <span>
                                        HABITAT
                                    </span>

                                    <strong id="animalHabitat">
                                        SAVANNAH
                                    </strong>

                                </div>


                                <div class="stat">

                                    <span>
                                        DIET
                                    </span>

                                    <strong id="animalDiet">
                                        CARNIVORE
                                    </strong>

                                </div>

                            </div>


                            <div class="fact-box">

                                <span>
                                    FUN FACT
                                </span>

                                <p id="animalFact">
                                    Lions are known as the kings of the jungle.
                                </p>

                            </div>

                        </div>


                        <div class="card-bottom">

                            <span>
                                ANIMAL CARDS
                            </span>

                            <span>
                                ★
                            </span>

                        </div>

                    </div>

                </div>


                <button
                    class="arrow arrow-right"
                    id="nextButton"
                    aria-label="Next card"
                >
                    ❯
                </button>


            </section>


            <div class="navigation-info">

                <span id="navigationText">
                    Unlock your first card!
                </span>

            </div>


        </main>

    </div>


    <script src="script.js"></script>

</body>

</html>
