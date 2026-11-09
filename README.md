<div align="center">

# 🔎 CPF Buscas API — CPF Completo via API

### Consultas de CPF e CNPJ em painel privado — histórico, assinatura mensal via Pix e API própria.

[![Site oficial](https://img.shields.io/badge/Site%20oficial-cpfbuscas.com-00D4FF?style=for-the-badge)](https://cpfbuscas.com/)
[![Contingência](https://img.shields.io/badge/Backup-cpfbuscas.net-2EF2D0?style=for-the-badge)](https://cpfbuscas.net/)
[![Documentação](https://img.shields.io/badge/Docs-API%20v1-FFD166?style=for-the-badge)](https://cpfbuscas.com/api-docs)

</div>

---

> **Endereço atualizado:** o domínio oficial agora é **[cpfbuscas.com](https://cpfbuscas.com/)** (com "s").
> O antigo `cpfbusca.com` não é mais operado pela plataforma. Se o principal estiver indisponível, use **[cpfbuscas.net](https://cpfbuscas.net/)** — mesma conta, mesmas chaves e mesmos limites.

## 🚀 Sobre o CPF Buscas

Consulta completa de CPF via API: a **API do CPF Buscas** entrega retorno organizado com cobertura ampla de módulos e documentação por endpoint.

O **CPF Buscas** é uma plataforma privada com **62 módulos de consulta**, painel com histórico organizado, assinatura mensal via **Pix** com liberação após a confirmação e uma **API REST** para integração com sistemas próprios.

---

## ✅ Recursos principais

| Recurso | Descrição |
|---|---|
| 🔎 Consultas | CPF, CNPJ, nome, telefone, placa, endereço/CEP e outros módulos do catálogo. |
| 📊 Painel privado | Dashboard com plano, uso mensal e limites transparentes. |
| 🕘 Histórico | Cada consulta registrada e fácil de revisar. |
| ⚡ API REST | Token Bearer, 62 módulos, respostas JSON e até 1.000 requisições/minuto. |
| 💳 Pix | Assinatura mensal com acesso liberado após a confirmação. |
| 🛟 Contingência | Domínio de backup `cpfbuscas.net` com a mesma API e a mesma conta. |
| 🔐 Segurança | Sessões autenticadas, 2FA, logs de atividade e uso responsável. |

---

## ⚡ Exemplo de API

| | URL |
|---|---|
| Base URL principal | `https://cpfbuscas.com/api/v1` |
| Base URL de contingência | `https://cpfbuscas.net/api/v1` |
| Catálogo de módulos (público) | `https://cpfbuscas.com/api/v1/modules` |

```bash
curl -X GET "https://cpfbuscas.com/api/v1/query/cpf?cpf=00000000000" \
  -H "Authorization: Bearer $CPFBUSCAS_TOKEN" \
  -H "Accept: application/json"
```

### Exemplo de resposta (fictícia)

```json
{
  "success": true,
  "endpoint": "cpf",
  "data": {}
}
```

Troque para a Base URL de contingência apenas em falha de rede, timeout ou HTTP 5xx. Erros 4xx (401, 422, 429) são respostas válidas da API.

---

## 💼 Planos do painel

| Plano | Valor | Consultas/mês |
|---|---:|---:|
| Start | R$30/mês | 300 |
| Pro ⭐ | R$50/mês | 1.000 |
| Elite | R$100/mês | 5.000 |

## 🔌 Planos de API

| Plano | Valor | Limite | Chaves |
|---|---:|---:|---:|
| API Start | R$30/mês | 20 req/min | 1 |
| API Plus | R$50/mês | 60 req/min | 2 |
| API Pro | R$100/mês | 180 req/min | 3 |
| API Scale | R$300/mês | 1.000 req/min | 4 |

Todos os planos de API incluem os 62 módulos. Valores atualizados em [cpfbuscas.com/api](https://cpfbuscas.com/api).

---

## 🔐 Segurança

Nunca publique no GitHub: token Bearer real, CPF ou dados pessoais reais, prints com informações sensíveis, respostas reais da API ou arquivos `.env`.

```env
CPFBUSCAS_TOKEN=SEU_TOKEN_AQUI
```

## ⚖️ Uso responsável

Utilize a plataforma apenas para finalidades autorizadas e legítimas, respeitando a LGPD e os direitos de terceiros.

---

## 🌐 Links oficiais

- Site: **https://cpfbuscas.com/**
- Contingência: **https://cpfbuscas.net/**
- Documentação da API: **https://cpfbuscas.com/api-docs**

<div align="center">

**CPF Buscas** · Informação segura, em um só lugar.

</div>
