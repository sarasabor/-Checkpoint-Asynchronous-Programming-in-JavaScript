# -Checkpoint-Asynchronous-Programming-in-JavaScript

Tâche 01: Itérer avec Async/Await
Écrivons une fonction iterateWithAsyncAwait qui prend un tableau de valeurs et enregistre chaque valeur avec un délai de 1 seconde entre les enregistrements.

javascript
async function iterateWithAsyncAwait(values) {  
    for (const value of values) {  
        console.log(value); // Enregistre la valeur  
        await new Promise(resolve => setTimeout(resolve, 1000)); // Attends 1 seconde  
    }  
}  

// Exemple d'utilisation  
iterateWithAsyncAwait(['A', 'B', 'C', 'D']);  
Tâche 02: Attendre un appel
Créons une fonction asynchrone awaitCall qui simule l'obtention de données à partir d'une API. Nous utiliserons await pour attendre la réponse de l'API.

javascript
async function awaitCall() {  
    // Simulation d'un appel API avec une promesse  
    const fetchData = () => new Promise(resolve => {  
        setTimeout(() => {  
            resolve('Données récupérées !');  
        }, 2000); // Simule un délai de 2 secondes  
    });  

    const data = await fetchData(); // Attends la réponse  
    console.log(data); // Enregistre les données  
}  

// Exemple d'utilisation  
awaitCall();  
Tâche 03: Gérer les erreurs avec Async/Await
Modifions la fonction awaitCall pour gérer les erreurs de manière élégante.

javascript
async function awaitCall() {  
    const fetchData = () => new Promise((resolve, reject) => {  
        setTimeout(() => {  
            const isError = Math.random() < 0.5; // Simule une erreur aléatoire  
            if (isError) {  
                reject(new Error("Erreur lors de la récupération des données !"));  
            } else {  
                resolve('Données récupérées avec succès !');  
            }  
        }, 2000);  
    });  

    try {  
        const data = await fetchData(); // Attends la réponse  
        console.log(data); // Enregistre les données  
    } catch (error) {  
        console.error(error.message); // Gère l'erreur  
    }  
}  

// Exemple d'utilisation  
awaitCall();  
Résumé
Tâche 01 : iterateWithAsyncAwait itère à travers un tableau avec un setTimeout pour créer une pause d'une seconde.
Tâche 02 : awaitCall simule un appel API et utilise await pour attendre les données.
Tâche 03 : awaitCall a été modifié pour gérer les erreurs avec un bloc try/catch.
