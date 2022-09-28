<template>
    <div class="container">
        <form class="formulario">
            

            <div class="campo">
                <div class="img-label">
                <img class="imagen-formulario" src="../assets/images/image.png" />
                <label for="nueva tarea">Nueva Tarea:</label>
                </div>
                <div>
                    <input type="text" placeholder="Nueva Tarea" id="nueva-tarea" />
                    <input type="submit" value="Agregar Nueva Tarea" />
                </div>
            </div>
        </form>
        <div class="tareas">
            <div>
                <h2>Tareas Pendientes</h2>
                <ul class="tareas-pendientes"></ul>
            </div>
            <div>
                <h2>Tareas Finalizadas</h2>
                <ul class="tareas-finalizadas"></ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {

};
</script>

<style scoped>
*:before, *:after{
    box-sizing: inherit;
}
.container {
    max-width: 120rem;
    width: 100vh;
    background-color: white;
    margin: 0 auto;
    border-radius: 1.5rem;
    padding: 1rem;
}

@media (min-width: 992px) {
    .container {
        display: grid;
        grid-template-rows: (2, 1fr);
        gap: 1.5rem;
        height: auto;
    }
}

.formulario {
    padding: 4rem 2rem;
    grid-row: 1 / 3;
}

.formulario label {
    font-size: 3rem;
}

@media (min-width: 768px) {
    .formulario input {
       flex: auto;
    }
}

.formulario input[type="text"] {
    padding: 1rem;
    width: 50vh;
}

.formulario input[type="submit"] {
    border: none;
    padding: 1rem 2rem;
    background-color: rgb(0, 140, 255);
    color: white;
    font-weight: 700;
    transition-property: background-color;
    transition-duration: 0.3s;
    border-radius: .5rem;
    font-size: 1.5rem;
}

.formulario input[type="submit"]:hover {
    background-color: rgb(0, 120, 218);
    cursor: pointer;
}

.imagen-formulario {
    width: 5rem;
}

.campo:first-of-type {
    margin-top: 2rem;
}

.campo div {
    display: flex;
    gap: 1rem;
}

@media (min-width: 768px) {
    .campo div:nth-child(2) {
        flex-direction: row;
        gap: 2rem;
    }
}
.img-label{
    margin-bottom: 1rem;
}
.tareas h2 {
    padding: 0 2rem;
}
.tareas-pendientes {
    list-style: none;
    padding: 2rem;
    border-bottom: 2px dashed #e1e1e1;
    margin: 0;
}

.tareas-pendientes li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 4rem;
    padding: 1rem 0;
    border-bottom: 1px solid #e1e1e1;
}

.tareas-pendientes li:last-of-type {
    margin-bottom: 0;
}

.iconos {
    display: flex;
    gap: 2rem;
}

.iconos img {
    width: 2rem;
    height: 2rem;
}

.iconos img {
    cursor: pointer;
}

.tareas-finalizadas {
    grid-column: 2 / 3;
    list-style: none;
    margin: 0;
    padding: 2rem;
}

.tareas-finalizadas li {
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-bottom: 1px solid #e1e1e1;
}

@media (min-width: 448px) {
    .tareas-finalizadas li {
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
}

.alerta {
    background-color: rgb(219, 33, 0);
    padding: 1rem 0;
    text-align: center;
    color: #e1e1e1;
    font-weight: bold;
    margin: 1rem 0;
    font-size: 1.5rem;
}

</style>
