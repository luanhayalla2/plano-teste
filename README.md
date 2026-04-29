# 🎓 SistemaAlunos: Engine de Cálculo de Médias

![Node.js](https://img.shields.io/badge/-Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Jest](https://img.shields.io/badge/-Jest-C21325?style=for-the-badge&logo=jest&logoColor=white)
![Coverage](https://img.shields.io/badge/Coverage-100%25-brightgreen?style=for-the-badge)

Este módulo é o núcleo de um sistema escolar, responsável por processar notas de alunos e determinar automaticamente seu status acadêmico. Foi desenvolvido como um estudo de caso para **Testes Unitários** e **Análise de Valor Limite (BVA)**.

---

## ⚙️ Funcionalidades Principais

O sistema é composto por duas funções core exportadas em `sistemaAlunos.js`:

1.  **`calcularMedia(notas)`**:
    *   Recebe um array de números.
    *   Retorna a média aritmética arredondada para 2 casas decimais.
    *   Trata entradas vazias ou inválidas retornando `0`.

2.  **`verificarStatus(media)`**:
    *   Analisa a média final e aplica as regras de negócio:
        *   **7.0 a 10.0**: `Aprovado`
        *   **5.0 a 6.9**: `Recuperação`
        *   **0.0 a 4.9**: `Reprovado`
    *   Lança erros para entradas fora do intervalo padrão (0-10).

---

## 📊 Estratégia de QA

A bateria de testes em `sistemaAlunos.test.js` foi projetada para garantir que nenhuma transição de status falhe. Utilizamos a técnica de **Análise de Valor Limite (BVA)** para testar exatamente as fronteiras de decisão.

### Tabela de Fronteiras Testadas:

| Valor | Categoria | Esperado |
| :--- | :--- | :--- |
| `7.0` | Limite de Aprovação | Aprovado |
| `6.9` | Logo abaixo de 7.0 | Recuperação |
| `5.0` | Limite de Recuperação | Recuperação |
| `4.9` | Logo abaixo de 5.0 | Reprovado |
| `0.0` | Limite Mínimo | Reprovado |
| `-1.0`| Fora da Faixa | Erro |

---

## 🛠️ Como Utilizar

### Instalação
```bash
npm install
```

### Executar Testes com Cobertura
```bash
npm test
```

A saída exibirá uma tabela de cobertura mostrando **100%** de aproveitamento em todas as funções e ramificações (branches).

---
*Documentação gerada pelo Antigravity AI Assistant.*
