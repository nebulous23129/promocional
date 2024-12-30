# Checkout7Pay

Sistema de checkout modular e escalável para processamento de pagamentos, com integração Pagar.me e rastreamento via Pixel do Facebook.

## Funcionalidades Principais

- Cadastro e gerenciamento de produtos
- Checkout em múltiplas etapas (dados pessoais, endereço, pagamento)
- Integração com Pagar.me
- Pixel do Facebook para rastreamento de eventos
- Consulta automática de CEP via ViaCEP
- Design responsivo inspirado no padrão Stripe
- Order Bump e Upsell
- Múltiplas formas de pagamento com descontos
- Sistema de webhooks para notificações

## Tecnologias Utilizadas

### Backend
- FastAPI: Framework web moderno e rápido
- SQLAlchemy: ORM para PostgreSQL
- Pydantic: Validação de dados
- Python-Jose: Implementação JWT
- Pagarme: SDK oficial do Pagar.me
- Facebook Business: SDK para integração com Pixel
- Nanoid: Geração de IDs únicos

### Frontend (Next.js)
- React.js/Next.js
- Tailwind CSS
- React Query
- Cleave.js
- Yup + Formik
- Framer Motion
- Axios

## Configuração do Ambiente

1. Crie um ambiente virtual Python:
```bash
python -m venv venv
```

2. Ative o ambiente virtual:
- Windows:
```bash
.\venv\Scripts\activate
```
- Linux/Mac:
```bash
source venv/bin/activate
```

3. Instale as dependências:
```bash
pip install -r requirements.txt
```

## Estrutura do Projeto

```
checkout7pay/
├── app/
│   ├── api/
│   │   ├── routes/
│   │   │   ├── admin.py
│   │   │   ├── checkout.py
│   │   │   └── webhooks.py
│   │   └── deps.py
│   ├── core/
│   │   ├── config.py
│   │   └── security.py
│   ├── models/
│   │   ├── product.py
│   │   ├── order.py
│   │   └── payment.py
│   ├── services/
│   │   ├── pagarme.py
│   │   ├── facebook.py
│   │   └── viacep.py
│   └── utils/
│       ├── validators.py
│       └── helpers.py
├── frontend/
│   ├── components/
│   ├── pages/
│   └── styles/
└── tests/
```

## Rotas Principais

- `/dashadmin`: Painel administrativo para gestão de produtos
- `/{iddoproduto}`: Página de checkout do produto
- `/statusdopedido`: Página de confirmação do pedido

## Eventos do Pixel do Facebook

- `addToCart`: Ao carregar página do checkout
- `initiateCheckout`: Ao preencher email
- `addPaymentInfo`: Ao completar endereço
- `purchase`: Ao finalizar compra

## Design

### Paleta de Cores
- Primária: `#65D19C`
- Secundária: `#F4F6F8`
- Destaque: `#D4D4D5`

### Fonte
- Inter ou Roboto
