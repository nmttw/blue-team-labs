# 🚨 Resposta a Incidente – SSH Brute Force

## 📌 Identificação do Incidente

- **Tipo:** Tentativa de acesso não autorizado
- **Serviço afetado:** SSH
- **Data/Hora:** Jan 15 – 10:12
- **Origem:** IP externo
- **Status:** Tentativas bloqueadas (sem comprometimento confirmado)

---

## 🔍 Descrição

Foi identificado um padrão de múltiplas falhas de autenticação no serviço SSH,
caracterizando um possível ataque de **brute force**. As tentativas ocorreram em
intervalos curtos, utilizando usuários comuns e privilegiados.

---

## 🧾 Evidências

- Logs do serviço SSH indicando falhas consecutivas
- Tentativas com usuários inválidos (`admin`, `root`, `test`, `guest`)
- Origem única do endereço IP `192.168.1.10`

Arquivo analisado:
- `logs/ssh/ssh-bruteforce.log`

---

## ⚠️ Classificação

- **Categoria:** Ataque externo
- **Severidade:** Média
- **Impacto:** Nenhum acesso confirmado
- **Probabilidade:** Alta (atividade automatizada)

---

## 🛑 Contenção

- Bloqueio temporário do IP de origem no firewall
- Monitoramento reforçado do serviço SSH
- Verificação de tentativas similares de outros IPs

---

## 🧹 Erradicação

- Confirmação de inexistência de acessos bem-sucedidos
- Revisão de configurações de autenticação SSH
- Garantia de que usuários testados não existem no sistema

---

## 🔄 Recuperação

- Manutenção do serviço SSH em operação
- Continuidade do monitoramento pós-incidente
- Ajuste de regras de alerta para novas tentativas

---

## 📚 Lições Aprendidas

- Ataques de brute force são frequentes em serviços expostos
- Políticas de bloqueio automático reduzem risco
- Alertas antecipados agilizam resposta do SOC

---

## 📝 Observações Finais

Este incidente reforça a importância de monitoramento contínuo e análise
proativa de logs em ambientes expostos à internet.
