# Desafio Dio Compartilhando o seu Projeto com o Mundo



**Projeto completo e abrangente com mais códigos para compartilhar seu projeto com o mundo:**

**Objetivo:** Compartilhar seu projeto do Unity com outras pessoas de forma colaborativa. Publicar um jogo desenvolvido com o Unity em várias plataformas.



## **Recursos:**

- **Unity Editor**
- **Conta no GitHub ou Bitbucket**
- **Arquivos do projeto**
- **Software de controle de versão (por exemplo, Git)**



### **Passos:**

**1. Crie um repositório no GitHub ou Bitbucket.**



**2. Clone o repositório para o seu computador.**



**3. Importe os arquivos do projeto para o Unity.**



**4. Faça alterações no projeto.**



**5. Adicione seus arquivos alterados ao controle de versão.**



**6. Confirme suas alterações com uma mensagem de confirmação descritiva.**



**7. Envie suas alterações para o repositório remoto.**



**8. Crie um pull request para mesclar suas alterações com a branch principal.**



#### **9. Revise as alterações do pull request e mescle-as na branch principal.**



### **Códigos e aplicabilidade:**



**Exemplo de código para adicionar arquivos ao controle de versão:**

plaintext



```plaintext
git add .
```



**Exemplo de código para confirmar alterações:**

plaintext



```plaintext
git commit -m "mensagem de confirmação"
```



**Exemplo de código para enviar alterações:**

plaintext



```plaintext
git push origin master
```



**Exemplo de código para criar um pull request:**

plaintext



```plaintext
git checkout master
git pull origin master
git checkout new-branch
git merge master
git push origin new-branch
```



**Recursos adicionais:**



- Documentação da Unity sobre controle de versão
- Tutorial da Unity sobre como usar o GitHub
- Tutorial da Unity sobre como usar o Bitbucket
- Documentação do Git



**Códigos adicionais:**



**Exemplo de código para criar um novo repositório no GitHub:**

plaintext



```plaintext
git init
git remote add origin https://github.com/username/repository.git
git add .
git commit -m "mensagem de confirmação inicial"
git push -u origin master
```



**Exemplo de código para criar um novo repositório no Bitbucket:**

plaintext



```plaintext
git init
git remote add origin https://bitbucket.org/username/repository.git
git add .
git commit -m "mensagem de confirmação inicial"
git push -u origin master
```



**Exemplo de código para criar um branch no GitHub ou Bitbucket:**

plaintext



```plaintext
git branch new-branch
git checkout new-branch
```



**Exemplo de código para mesclar um branch no GitHub ou Bitbucket:**

plaintext



```plaintext
git checkout master
git merge new-branch
```



### **Dicas para colaboração:**



- Use branches para trabalhar em recursos ou correções específicos.
- Crie pull requests para revisar e mesclar suas alterações com a branch principal.
- Comunique-se com seus colaboradores por meio de comentários e discussões no repositório.
- Mantenha seu repositório atualizado puxando as alterações mais recentes regularmente.





### **Projeto aprimorado com mais códigos e exemplos:**



### **Iluminação:**

csharp



```csharp
// Configuração de luz ambiente
Light ambientLight = new Light();
ambientLight.Color = Color.Gray;
ambientLight.Intensity = 0.5f;

// Configuração de luz direcional (sol)
Light directionalLight = new Light();
directionalLight.Type = LightType.Directional;
directionalLight.Direction = new Vector3(0.5f, -0.7f, 0.3f);
directionalLight.Intensity = 1.0f;
```



### **Mecânicas de Ataque:**

csharp



```csharp
// Ataques básicos: Ataque de espada
void Update()
{
    if (Input.GetMouseButtonDown(0))
    {
        // Detectar inimigos próximos
        Collider[] enemies = Physics.OverlapSphere(transform.position, attackRange);
        foreach (Collider enemy in enemies)
        {
            // Aplicar dano ao inimigo
            enemy.GetComponent<EnemyHealth>().TakeDamage(20);
        }
    }
}
```



csharp



```csharp
// Combos: Ataque de espada com sequência de botões
void Update()
{
    if (Input.GetKeyDown(KeyCode.Space))
    {
        if (attackCombo == 0)
        {
            attackCombo = 1;
            Invoke("ResetAttackCombo", 1.0f); // Redefine o combo após 1 segundo
        }
        else if (attackCombo == 1)
        {
            attackCombo = 2;
            // Aplicar dano maior para o segundo ataque do combo
            enemy.GetComponent<EnemyHealth>().TakeDamage(30);
        }
    }
}

void ResetAttackCombo()
{
    attackCombo = 0;
}
```



csharp



```csharp
// Sistema de dano: Reação do inimigo ao ataque
public class EnemyHealth : MonoBehaviour
{
    public float health = 100.0f;

    public void TakeDamage(float damage)
    {
        health -= damage;
        // Animação de dano, efeitos sonoros etc.
        if (health <= 0.0f)
        {
            // Morrer
        }
    }
}
```



### **Interação com Objetos:**

csharp



```csharp
// Portas e alavancas: Abrir porta com chave
void OnInteract()
{
    if (playerHasKey)
    {
        // Abrir a porta
        doorAnimator.SetTrigger("Open");
        playerHasKey = false; // Remove a chave do inventário do jogador
    }
    else
    {
        // Exibir mensagem de que a porta está trancada
        UIManager.ShowMessage("A porta está trancada. Encontre a chave!");
    }
}
```



csharp



```csharp
// Coleta de itens: Pegar itens
void OnCollisionEnter(Collider other)
{
    if (other.CompareTag("Item"))
    {
        // Adicionar item ao inventário do jogador
        playerInventory.AddItem(other.gameObject);
        Destroy(other.gameObject); // Remover o item da cena
    }
}
```



csharp



```csharp
// Quebra de objetos: Quebrar caixas
void OnCollisionEnter(Collider other)
{
    if (other.CompareTag("Breakable"))
    {
        // Aplicar força para quebrar o objeto
        other.GetComponent<Rigidbody>().AddForce(Vector3.up * 1000.0f);
        // Spawnar itens ou efeitos de partículas
    }
}
```



Esses códigos e exemplos aprimorados fornecem uma implementação mais abrangente e detalhada dos recursos mencionados em seu projeto anterior.
