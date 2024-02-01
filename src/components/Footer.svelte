<footer>
    <div class="question">Wanna buy?</div>
    <div class="contacts">
        <div>buy <a class="gallery-link" href="https://artonline24.ru/artists/info/8608/"> <span class="underline">here</span></a> or email:&nbsp;</div>
        <div><a href="mailto:zverevaekatval@gmail.com">
            <i class="fa-regular fa-envelope"></i> zverevaekatval@gmail.com
        </a></div>
    </div>
</footer>

<style>
    footer {
    margin-top: 50px;
    height: 100px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: black;
    font-weight: 600;
    }

    footer a {
    color: black;      /* наследовать цвет текста от родителя */
    text-decoration: none; /* убрать подчеркивание */
    background-color: transparent; /* прозрачный фон */
    cursor: pointer; /* изменить курсор на указатель */
    }

    .contacts {
        text-align: center;
        display: flex;
        flex-direction: row;
    }

    .question {
        font-size: 1.2rem;
        font-weight: 700;
    }

    .underline {
        text-decoration: underline;
    }

    @media (max-width: 600px) {
        .contacts {
            flex-direction: column;
        }
    }
</style>