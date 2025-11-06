<div class = "container">
            <header>
                <h1><i class = "fas fa-utensils"></i> Recipe Finder</h1>
                <p>Find delicious recipes from around the world</p>
            </header>

            <p class = "api-link">
                Data from <a href = "https://www.themealdb.com/api-php">TheMealDB (A glass cup here)</a>
            </p>

            <div class = "search-container">
                <input type = "text" id = "search-input" placeholder = "Search for meals or keyword">
                <button id = "search-btn">Search</button>
            </div>

            <div id = "error-container" class = "hidden">
                <p>No meals found. Try another search term.</p>
            </div>

            <div id = "result-heading"></div>

            <div id = "meals" class = "meals-container"></div>

            <div id = "meal-details" class = "hidden">
                <button id = "back-btn"><i class = "fas fa-arrow-left"></i> Back to recipes</button>

                <div class = "meal-details-content"></div>
            </div>
        </div>

const searchInput = document.getElementById("search-input");
const searchBtn = document.getElementById("search-btn");
const errorContainer = document.getElementById("error-container");
const resultHeading = document.getElementById("result-heading");
const mealsContainer = document.getElementById("meals");
const mealDetails = document.getElementById("meal-details");
const backBtn = document.getElementById("back-btn");
const mealDetailsContent = document.querySelector(".meal-details-content");


const BASIC_URL = "https://www.themealdb.com/api/json/v1/1/"
const SEARCH_URL = `${BASIC_URL}search.php?s=`
const LOOKUP_URL = `${BASIC_URL}lookup.php?i=`


searchBtn.addEventListener("click", searchMeals);

mealsContainer.addEventListener("click", handleMealClick);

backBtn.addEventListener("click", () => mealDetails.classList.add("hidden"));

searchInput.addEventListener("keypress", (e) => {
    if (e.key == "Enter") searchMeals()

})


async function searchMeals () {
       const searchTerm = searchInput.value.trim()

       if (!searchTerm) {
        errorContainer.textContent = "Please enter a search term";
        errorContainer.classList.remove("hidden");

        return;

       }

}