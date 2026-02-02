# 🚨 Detecção – SSH Brute Force

## 📌 Descrição

Ataques de **SSH brute force** consistem em múltiplas tentativas de autenticação
utilizando diferentes usuários e/ou senhas, geralmente de forma automatizada.

Este tipo de ataque é comum em servidores expostos à internet e pode indicar
tentativa de acesso não autorizado.

---

## 🔍 Evidências Observadas

Analisando o arquivo `logs/ssh/ssh-bruteforce.log`, foram identificados:

- Múltiplas falhas de autenticação
- Tentativas com usuários inválidos (`admin`, `root`, `test`, `guest`)
- Origem única do endereço IP `192.168.1.10`
- Intervalos curtos entre as tentativas

---

## 🧾 Indicadores de Comprometimento (IOCs)

| Tipo | Valor |
|----|----|
| IP de origem | 192.168.1.10 |
| Serviço alvo | SSH |
| Porta | 22 |
| Usuários testados | admin, root, test, guest |

---

## 📐 Critérios de Detecção

Um evento pode ser considerado **suspeito** quando:

- O mesmo IP realiza **5 ou mais falhas de login**
- Em um intervalo inferior a **1 minuto**
- Utilizando usuários inexistentes ou privilegiados

---

## ⚠️ Severidade

**Média**

Apesar de não haver sucesso na autenticação, o volume e padrão das tentativas
indicam atividade automatizada e maliciosa.

---

## 📝 Observações

- Ataques de brute force são frequentemente precursores de acessos indevidos
- Monitoramento contínuo e alertas são recomendados
- Este evento deve ser correlacionado com outros logs do ambiente
