# Site de Inscrição com HTML CSS JS 

A **RocketSeat** nos proporcionou esse treinamento, criando um site de inscrição, com funcionalidades simples, porém funcional.

<tr>

#Funcionalidades do site: 

O JavaScript está trabalhando em toda parte lógica e estrutural do site: 
<br>

1.Const com arry de usuários cadastrados:
```JS
const users = [
   {
    email: "test@test.com",
    phone: "999999999999",
    ref: 100,
    refBy: null
   },
   {
    email: "tust@tust.com",
    phone: "999999999999",
    ref:300,
    refBy: 100
   },
   {
    email: "tost@tost.com",
    phone: "999999999999",
    ref:400,
    refBy: 100
   }
]
```
<br>
2. Encontrar usuários cadastrados e retornar a quantidade de usuários: 

```JS

const getUser = (userData) => {
    return users.find((user) =>{ 
        return user.email == userData.email
})
}
const getTotalSubscribers = (userData) => {
    const subs = users.filter((user) => {
        return user.refBy == userData.ref
    })
    return subs.length
}
```
<br>

3. Inserindo o código HTML pelo JavaScript

```
const showInvite = (userData) =>{
    app.innerHTML = `  
    <main>
        <h3>Inscrição Confirmada</h3>
        <p>
           Convide mais pessoas e concorra a prêmios!<br>
           Compartilhe o link e acompanhe as inscrições:
            
        </p>
<div class="input-group">
    <label for="link">
        <img src="link.svg" alt="Link icon">
    </label>
     <input type="text" id="link" value="https://evento.com?ref=${userData.ref}" disabled>
</div>
    </main>
    <section class="stats">
          <h4>
            ${getTotalSubscribers(userData)}
        </h4>
        <p>
            Inscrições feitas
        </p>
    </section>
```

<tr>
