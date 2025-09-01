# Instruções personalizadas para GitHub Copilot

Este projeto utiliza **PHP Generator for MySQL** na versão **22.8.0.19** (release 22/05/2025) como framework principal.  
O código deve seguir boas práticas de organização, reaproveitamento e integração com o gerador.

---

## Tecnologias utilizadas
- **PHP** (backend)
- **JavaScript**
- **jQuery / Ajax** (requisições assíncronas e interatividade)
- **Bootstrap v4.1.3** (UI)
- **MySQL** (banco de dados)

---

## Convenções de código
1. Sempre usar **PHP 7.4+** com tipagem quando possível.
2. No JavaScript, priorizar **jQuery** para seletores, eventos e Ajax.
3. Estruturar Ajax com:
   - `$.ajax()` ou `$.post()` / `$.get()`
   - Respostas no formato JSON
   - Tratamento de erros (`error` ou `fail`)
4. No PHP Generator:
   - Usar **eventos do framework** (BeforeInsert, BeforeUpdate, CustomTemplate, etc.).
   - Personalizações devem ser feitas via **User functions** e não diretamente no core do framework.
5. Para estilos visuais, seguir o padrão **Bootstrap 4.1.3**.
6. Comentários devem ser claros, em **português**, explicando a regra de negócio.

---

## Exemplos de uso

### Ajax com PHP Generator
```javascript
$.ajax({
  url: 'minha_funcao.php',
  method: 'POST',
  data: { id: 123 },
  dataType: 'json',
  success: function(response) {
    if (response.success) {
      alert('Operação concluída!');
    } else {
      alert('Erro: ' + response.message);
    }
  },
  error: function() {
    alert('Falha na comunicação com o servidor.');
  }
});
