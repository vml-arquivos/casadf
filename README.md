# CasaDF - Sistema Imobiliário Completo

Sistema completo de gerenciamento imobiliário com CRM integrado, site público, inteligência artificial e automações.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node](https://img.shields.io/badge/node-22.x-green.svg)
![React](https://img.shields.io/badge/react-18.x-blue.svg)
![TypeScript](https://img.shields.io/badge/typescript-5.x-blue.svg)
![PostgreSQL](https://img.shields.io/badge/postgresql-16-blue.svg)

## 🚀 Tecnologias

- **Backend**: Node.js 22 + Express + tRPC + PostgreSQL + Drizzle ORM
- **Frontend**: React 18 + Vite + TailwindCSS + Wouter
- **DevOps**: Docker + Docker Compose + pnpm
- **Integrações**: Manus OAuth + Google Gemini (IA) + N8N + AWS S3

## 📋 Início Rápido

```bash
# 1. Clone o repositório
git clone https://github.com/vml-arquivos/casadf.git
cd casadf

# 2. Instale dependências
pnpm install

# 3. Configure variáveis de ambiente
cp .env.example .env
# Edite o .env com suas credenciais

# 4. Inicie o banco de dados (Docker)
docker compose up -d db

# 5. Aplique migrations
pnpm db:generate
pnpm db:push

# 6. Inicie o servidor de desenvolvimento
pnpm dev
```

Acesse: http://localhost:3000

## 🐳 Deploy com Docker

```bash
# Deploy completo (produção)
docker compose up -d --build

# Verificar status
docker compose ps
docker compose logs -f app

# Acessar aplicação
curl http://localhost:3000/health
```

## 📦 Scripts Disponíveis

```bash
pnpm dev              # Desenvolvimento
pnpm build            # Build produção
pnpm start            # Iniciar produção
pnpm db:generate      # Gerar migrations
pnpm db:push          # Aplicar migrations
pnpm db:studio        # Interface visual do banco
pnpm test             # Executar testes
```

## 🎯 Funcionalidades

### CRM Imobiliário
- ✅ Gestão de imóveis (CRUD completo)
- ✅ Cadastro de proprietários
- ✅ Gestão de leads e pipeline
- ✅ Histórico de interações
- ✅ Analytics e métricas

### Site Público
- ✅ Listagem com filtros avançados
- ✅ Galeria de fotos
- ✅ Formulário de contato
- ✅ SEO otimizado
- ✅ Responsivo (mobile-first)
- ✅ Blog integrado

### Integrações
- ✅ WhatsApp via N8N (opcional)
- ✅ IA para atendimento (opcional)
- ✅ Analytics
- ✅ Storage de imagens (S3)

## 📊 Banco de Dados

PostgreSQL 16 com Drizzle ORM:
- users, properties, property_images
- owners, leads, interactions
- reviews, blog_posts, site_settings
- analytics_events, webhook_logs

## 🔧 Configuração

### Variáveis Obrigatórias

```env
DATABASE_URL=postgres://casadf_user:senha@localhost:5432/casadf_db
JWT_SECRET=your-secret-key
VITE_APP_ID=your-manus-app-id
OAUTH_SERVER_URL=https://oauth.manus.im
OWNER_OPEN_ID=your-owner-id
```

Ver `.env.example` para lista completa.

## 🚀 Deploy em Produção

### Requisitos
- CPU: 2 cores
- RAM: 2GB
- Storage: 20GB
- Docker 24.x+

### Passos

1. Clone no servidor
2. Configure `.env`
3. Execute `docker compose up -d --build`
4. Verifique `/health`
5. Configure Nginx (proxy reverso)

## 🛠️ Troubleshooting

```bash
# Erro de conexão com banco
docker compose logs db
docker compose down -v && docker compose up -d db

# Build falha
rm -rf node_modules dist
pnpm install && pnpm build

# Porta em uso
# Altere PORT no .env
```

## 📝 Licença

MIT License

## 👥 Suporte

- **Issues**: [GitHub Issues](https://github.com/vml-arquivos/casadf/issues)
- **Email**: contato@casadf.com.br

---

**Desenvolvido com ❤️ para o mercado imobiliário de Brasília**
