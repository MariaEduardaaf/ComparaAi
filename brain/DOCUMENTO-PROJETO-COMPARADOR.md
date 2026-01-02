# Documento de Especificação do Projeto
## App Comparador Inteligente Brasil

---

## 1. Visão Geral do Projeto

### 1.1 Nome do Projeto
**ComparaAí** (sugestão) - App Comparador Inteligente Multi-Vertical

### 1.2 Descrição
Plataforma móvel e web que funciona como um "personal shopper digital", permitindo aos usuários brasileiros comparar preços, qualidade e benefícios de múltiplos serviços e produtos em tempo real, com recomendações personalizadas baseadas em IA.

### 1.3 Proposta de Valor
- **Para o usuário**: Economizar tempo e dinheiro encontrando as melhores ofertas personalizadas
- **Para parceiros**: Acesso a leads qualificados e conversões diretas
- **Diferencial**: Único app no Brasil que integra múltiplas verticais com IA e contratação direta

### 1.4 Público-Alvo
- **Primário**: Adultos 25-45 anos, classe B e C, digitalmente ativos
- **Secundário**: Jovens 18-24 anos buscando primeiros serviços financeiros
- **Terciário**: Adultos 45+ buscando economia em serviços domésticos

---

## 2. Funcionalidades Principais

### 2.1 Comparação Multi-Vertical

#### Categorias de Serviços:

| Categoria | Serviços Incluídos | Prioridade |
|-----------|-------------------|------------|
| **Finanças** | Contas digitais, cartões de crédito, empréstimos pessoais, seguros (auto, vida, residencial), investimentos | Alta |
| **Telecomunicações** | Planos de celular, internet fixa, TV por assinatura, combos | Alta |
| **Energia** | Fornecedores de energia, energia solar, eficiência energética | Média |
| **Streaming** | Netflix, Spotify, Disney+, HBO Max, combos de streaming | Média |
| **Mobilidade** | Passagens aéreas, aluguel de carros, apps de transporte | Média |
| **E-commerce** | Comparação de preços de produtos em marketplaces | Baixa (fase 2) |

### 2.2 Motor de Recomendação com IA

```
┌─────────────────────────────────────────────────────────┐
│                  MOTOR DE RECOMENDAÇÃO                  │
├─────────────────────────────────────────────────────────┤
│  INPUTS:                                                │
│  - Perfil do usuário (idade, renda, localização)        │
│  - Histórico de consumo                                 │
│  - Preferências declaradas                              │
│  - Comportamento no app                                 │
│                                                         │
│  PROCESSAMENTO:                                         │
│  - Machine Learning para padrões de consumo             │
│  - Algoritmo de matching perfil x ofertas               │
│  - Score de relevância personalizado                    │
│                                                         │
│  OUTPUTS:                                               │
│  - Ranking personalizado de ofertas                     │
│  - Previsão de economia                                 │
│  - Alertas proativos                                    │
└─────────────────────────────────────────────────────────┘
```

### 2.3 Simulador de Economia

**Funcionalidades:**
- Cálculo de economia anual/mensal ao trocar de serviço
- Comparativo visual (gráficos) do antes vs depois
- Projeção de gastos futuros
- Análise de custo-benefício incluindo qualidade

**Exemplo de Output:**
```
┌────────────────────────────────────────┐
│  SIMULAÇÃO DE TROCA - PLANO INTERNET   │
├────────────────────────────────────────┤
│  Plano Atual: Vivo Fibra 300MB         │
│  Custo: R$ 149,90/mês                  │
│                                        │
│  Recomendação: Claro Fibra 500MB       │
│  Custo: R$ 119,90/mês                  │
│                                        │
│  ✅ Economia: R$ 30,00/mês             │
│  ✅ Economia Anual: R$ 360,00          │
│  ✅ Bônus: +200MB de velocidade        │
│  ⭐ Avaliação usuários: 4.2/5          │
└────────────────────────────────────────┘
```

### 2.4 Sistema de Alertas Inteligentes

| Tipo de Alerta | Descrição | Canal |
|----------------|-----------|-------|
| Queda de Preço | Serviço monitorado ficou mais barato | Push, Email |
| Promoção Exclusiva | Oferta especial para perfil do usuário | Push |
| Vencimento de Contrato | Lembrete para renegociar | Push, WhatsApp |
| Oportunidade de Economia | Nova opção melhor identificada | Push |
| Cashback Disponível | Recompensa pronta para resgate | Push |

### 2.5 Contratação Integrada

**Fluxo de Contratação:**
```
[Usuário escolhe oferta] 
       ↓
[Verifica dados do perfil]
       ↓
[Preenche informações adicionais (se necessário)]
       ↓
[Escolhe forma de pagamento]
       ↓
[Confirma contratação]
       ↓
[Recebe confirmação + acompanhamento]
```

**Integrações de Pagamento:**
- PIX
- Cartão de crédito/débito
- Carteiras digitais (PicPay, Mercado Pago, etc.)
- Débito automático

### 2.6 Sistema de Avaliações e Reputação

**Métricas Coletadas:**
- Avaliação geral (1-5 estrelas)
- Qualidade do atendimento
- Cumprimento do prometido
- Facilidade de cancelamento
- Custo-benefício percebido

**Dados de Performance Real:**
- Velocidade real de internet (via speed test integrado)
- Tempo de resposta de atendimento
- Taxa de reclamações (integração Reclame Aqui/Consumidor.gov)

---

## 3. Arquitetura Técnica

### 3.1 Visão Geral da Arquitetura (Simplificada - Desenvolvimento Solo)

```
┌─────────────────────────────────────────────────────────────────┐
│                      FRONTEND + BACKEND                         │
│                        (Next.js 14)                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                    Web App (PWA)                        │   │
│   │              Next.js + React + TypeScript               │   │
│   │                                                         │   │
│   │  ┌─────────────┐  ┌─────────────┐  ┌─────────────────┐  │   │
│   │  │   Pages/    │  │ Components  │  │   API Routes    │   │   │
│   │  │   App       │  │  (shadcn)   │  │   (Backend)     │   │   │
│   │  └─────────────┘  └─────────────┘  └─────────────────┘  │   │
│   │                                                         │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│                         Deploy: Vercel (grátis)                 │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│                         SUPABASE                                │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐     │
│   │ PostgreSQL  │  │    Auth     │  │   Storage (imgs)    │     │
│   │   (Dados)   │  │   (Login)   │  │     (opcional)      │     │
│   └─────────────┘  └─────────────┘  └─────────────────────┘     │
│                                                                 │
│                         Grátis até 500MB                        │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│                   INTEGRAÇÕES EXTERNAS                          │
├─────────────────────────────────────────────────────────────────┤
│         APIs de Afiliados (Lomadee, Awin, programas diretos)    │
└─────────────────────────────────────────────────────────────────┘
```

### 3.2 Stack Tecnológico (MVP - Desenvolvimento Solo)

| Camada | Tecnologia | Justificativa |
|--------|------------|---------------|
| **Framework Full-Stack** | Next.js 14 | Frontend + Backend em um só, SEO, grátis na Vercel |
| **Linguagem** | TypeScript | Menos bugs, melhor autocompletar |
| **UI Components** | Tailwind CSS + shadcn/ui | Componentes prontos, desenvolvimento rápido |
| **Banco de Dados** | Supabase (PostgreSQL) | Grátis, Auth incluso, fácil de usar |
| **Autenticação** | Supabase Auth | Login Google/Email pronto, sem custo |
| **Hospedagem** | Vercel | Deploy automático, grátis, CDN global |
| **Domínio** | Registro.br | ~R$ 40/ano |

### 3.2.1 Por que essa stack?

| Decisão | Motivo |
|---------|--------|
| **Next.js ao invés de React puro** | Já inclui backend (API Routes), SEO melhor, deploy fácil |
| **Supabase ao invés de Firebase** | PostgreSQL (mais robusto), pricing melhor ao escalar |
| **Vercel ao invés de AWS** | Zero configuração, grátis, perfeito para Next.js |
| **shadcn/ui ao invés de Material UI** | Mais leve, customizável, sem dependências pesadas |
| **Sem mobile nativo (por enquanto)** | Web responsivo primeiro, mobile depois se validar |

### 3.2.2 Custos da Stack

| Serviço | Plano | Custo |
|---------|-------|-------|
| Next.js | Open source | R$ 0 |
| Vercel | Hobby | R$ 0 |
| Supabase | Free | R$ 0 |
| Tailwind | Open source | R$ 0 |
| shadcn/ui | Open source | R$ 0 |
| GitHub | Free | R$ 0 |
| **Total** | | **R$ 0** |

### 3.3 Modelo de Dados (Principais Entidades)

```sql
-- Usuário
CREATE TABLE users (
    id UUID PRIMARY KEY,
    email VARCHAR(255) UNIQUE NOT NULL,
    phone VARCHAR(20),
    name VARCHAR(255),
    birth_date DATE,
    income_range VARCHAR(50),
    location_city VARCHAR(100),
    location_state VARCHAR(2),
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP
);

-- Perfil de Preferências
CREATE TABLE user_preferences (
    id UUID PRIMARY KEY,
    user_id UUID REFERENCES users(id),
    category VARCHAR(50),
    priority VARCHAR(20), -- 'price', 'quality', 'balance'
    notifications_enabled BOOLEAN DEFAULT true,
    created_at TIMESTAMP DEFAULT NOW()
);

-- Serviços/Produtos
CREATE TABLE services (
    id UUID PRIMARY KEY,
    provider_id UUID REFERENCES providers(id),
    category VARCHAR(50),
    name VARCHAR(255),
    description TEXT,
    price DECIMAL(10,2),
    features JSONB,
    region VARCHAR(100),
    is_active BOOLEAN DEFAULT true,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP
);

-- Fornecedores/Parceiros
CREATE TABLE providers (
    id UUID PRIMARY KEY,
    name VARCHAR(255),
    category VARCHAR(50),
    logo_url VARCHAR(500),
    website VARCHAR(500),
    api_integration BOOLEAN DEFAULT false,
    commission_rate DECIMAL(5,2),
    rating_avg DECIMAL(3,2),
    created_at TIMESTAMP DEFAULT NOW()
);

-- Avaliações
CREATE TABLE reviews (
    id UUID PRIMARY KEY,
    user_id UUID REFERENCES users(id),
    service_id UUID REFERENCES services(id),
    rating INTEGER CHECK (rating >= 1 AND rating <= 5),
    comment TEXT,
    verified_purchase BOOLEAN DEFAULT false,
    created_at TIMESTAMP DEFAULT NOW()
);

-- Contratações
CREATE TABLE contracts (
    id UUID PRIMARY KEY,
    user_id UUID REFERENCES users(id),
    service_id UUID REFERENCES services(id),
    status VARCHAR(50), -- 'pending', 'active', 'cancelled'
    contracted_price DECIMAL(10,2),
    commission_earned DECIMAL(10,2),
    created_at TIMESTAMP DEFAULT NOW()
);

-- Alertas
CREATE TABLE alerts (
    id UUID PRIMARY KEY,
    user_id UUID REFERENCES users(id),
    type VARCHAR(50),
    service_id UUID REFERENCES services(id),
    threshold_price DECIMAL(10,2),
    is_active BOOLEAN DEFAULT true,
    last_triggered TIMESTAMP,
    created_at TIMESTAMP DEFAULT NOW()
);
```

---

## 4. Fluxos de Usuário (UX)

### 4.1 Fluxo de Onboarding

```
┌─────────────────────────────────────────────────────────────┐
│                    TELA 1: BOAS-VINDAS                      │
│  ┌─────────────────────────────────────────────────────┐    │
│  │                                                     │    │
│  │              [Logo ComparaAí]                       │    │
│  │                                                     │    │
│  │     "Economize tempo e dinheiro                     │    │
│  │      comparando tudo em um só lugar"                │    │
│  │                                                     │    │
│  │         [Começar]  [Já tenho conta]                 │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    TELA 2: CADASTRO RÁPIDO                  │
│  ┌─────────────────────────────────────────────────────┐    │
│  │                                                     │    │
│  │     [Continuar com Google]                          │    │
│  │     [Continuar com Apple]                           │    │
│  │     ─────────── ou ───────────                      │    │
│  │     Email: [________________]                       │    │
│  │     Senha: [________________]                       │    │
│  │                                                     │    │
│  │         [Criar conta]                               │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                 TELA 3: PERSONALIZAÇÃO                      │
│  ┌─────────────────────────────────────────────────────┐    │
│  │                                                     │    │
│  │  "O que você quer comparar primeiro?"               │    │
│  │                                                     │    │
│  │  [ ] Planos de celular e internet                   │    │
│  │  [ ] Cartões de crédito e bancos                    │    │
│  │  [ ] Seguros (auto, vida, casa)                     │    │
│  │  [ ] Streaming (Netflix, Spotify...)               │    │
│  │  [ ] Energia elétrica                               │    │
│  │  [ ] Tudo acima!                                    │    │
│  │                                                     │    │
│  │         [Continuar]                                 │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   TELA 4: PERFIL BÁSICO                     │
│  ┌─────────────────────────────────────────────────────┐    │
│  │                                                     │    │
│  │  "Algumas infos para personalizar melhor:"          │    │
│  │                                                     │    │
│  │  Cidade: [São Paulo        ▼]                       │    │
│  │                                                     │    │
│  │  Faixa de renda mensal:                             │    │
│  │  ( ) Até R$ 3.000                                   │    │
│  │  ( ) R$ 3.000 - R$ 7.000                            │    │
│  │  ( ) R$ 7.000 - R$ 15.000                           │    │
│  │  ( ) Acima de R$ 15.000                             │    │
│  │  ( ) Prefiro não informar                           │    │
│  │                                                     │    │
│  │         [Finalizar]  [Pular]                        │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
```

### 4.2 Fluxo Principal de Comparação

```
┌─────────────────────────────────────────────────────────────┐
│                      HOME / DASHBOARD                       │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Olá, João!                      [Perfil] [Alertas] │    │
│  │                                                     │    │
│  │  ┌─────────────────────────────────────────────┐    │    │
│  │  │ Economia este mês: R$ 127,00              │    │    │
│  │  │ [Ver detalhes]                             │    │    │
│  │  └─────────────────────────────────────────────┘    │    │
│  │                                                     │    │
│  │  O que você quer comparar?                          │    │
│  │  ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐ ┌────┐         │    │
│  │  │Cell│ │Net │ │Bank│ │Seg │ │Strm│ │Enrg│         │    │
│  │  └────┘ └────┘ └────┘ └────┘ └────┘ └────┘         │    │
│  │                                                     │    │
│  │  Recomendações para você:                           │    │
│  │  ┌─────────────────────────────────────────────┐    │    │
│  │  │ Nubank Ultravioleta                        │    │    │
│  │  │ Cashback 1% | Sem anuidade | ⭐ 4.8        │    │    │
│  │  │ [Ver detalhes]                             │    │    │
│  │  └─────────────────────────────────────────────���    │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   LISTA DE COMPARAÇÃO                       │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Planos de Internet em São Paulo                    │    │
│  │  [Filtros: Preço ▼] [Velocidade] [Avaliação]        │    │
│  │                                                     │    │
│  │  ┌─────────────────────────────────────────────┐    │    │
│  │  │ 1. Claro Fibra 500MB           R$ 99,90    │    │    │
│  │  │    ⭐ 4.2 | Instalação grátis              │    │    │
│  │  │    Economia vs seu plano: R$ 50/mês        │    │    │
│  │  │    [Simular] [Contratar]                   │    │    │
│  │  └─────────────────────────────────────────────┘    │    │
│  │  ┌─────────────────────────────────────────────┐    │    │
│  │  │ 2. Vivo Fibra 400MB            R$ 109,90   │    │    │
│  │  │    ⭐ 4.5 | WiFi 6 incluso                 │    │    │
│  │  │    [Simular] [Contratar]                   │    │    │
│  │  └─────────────────────────────────────────────┘    │    │
│  │  ┌─────────────────────────────────────────────┐    │    │
│  │  │ 3. Tim Live 300MB              R$ 89,90    │    │    │
│  │  │    ⭐ 3.8 | Bônus: Tim Black              │    │    │
│  │  │    [Simular] [Contratar]                   │    │    │
│  │  └─────────────────────────────────────────────┘    │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   DETALHE DO SERVIÇO                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  [← Voltar]                                         │    │
│  │                                                     │    │
│  │  [Logo Claro]  Claro Fibra 500MB                    │    │
│  │                                                     │    │
│  │  R$ 99,90/mês                        [Contratar]    │    │
│  │                                                     │    │
│  │  ─────────────────────────────────────────────      │    │
│  │  Benefícios inclusos:                               │    │
│  │  ✓ 500 Mega de velocidade                          │    │
│  │  ✓ WiFi 5 incluso                                  │    │
│  │  ✓ Instalação gratuita                             │    │
│  │  ✓ Claro Vídeo grátis por 3 meses                  │    │
│  │                                                     │    │
│  │  ─────────────────────────────────────────────      │    │
│  │  Avaliações de usuários:              ⭐ 4.2/5     │    │
│  │  ┌─────────────────────────────────────────────┐    │    │
│  │  │ "Velocidade boa, atendimento ok" - Maria   │    │    │
│  │  │ ⭐⭐⭐⭐ - há 2 dias                       │    │    │
│  │  └─────────────────────────────────────────────┘    │    │
│  │  [Ver todas as 1.234 avaliações]                    │    │
│  │                                                     │    │
│  │  ─────────────────────────────────────────────      │    │
│  │  Simulação de economia:                             │    │
│  │  Seu plano atual: R$ 149,90                         │    │
│  │  Este plano: R$ 99,90                               │    │
│  │  Economia mensal: R$ 50,00                          │    │
│  │  Economia anual: R$ 600,00                          │    │
│  │                                                     │    │
│  │         [Criar Alerta]  [Contratar Agora]           │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
```

### 4.3 Fluxo de Contratação

```
┌─────────────────────────────────────────────────────────────┐
│                   CHECKOUT - PASSO 1                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Contratando: Claro Fibra 500MB                     │    │
│  │  Valor: R$ 99,90/mês                                │    │
│  │                                                     │    │
│  │  ─────────────────────────────────────────────      │    │
│  │  Confirme seus dados:                               │    │
│  │                                                     │    │
│  │  Nome: João Silva                    [Editar]       │    │
│  │  CPF: 123.456.789-00                 [Editar]       │    │
│  │  Endereço de instalação:                            │    │
│  │  Rua das Flores, 123 - São Paulo     [Editar]       │    │
│  │                                                     │    │
│  │         [Continuar]                                 │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   CHECKOUT - PASSO 2                        │
│  ┌─────────────────────────────────────────────────────┐    │
│  │  Forma de pagamento:                                │    │
│  │                                                     │    │
│  │  ( ) PIX - 5% de desconto                          │    │
│  │  ( ) Cartão de crédito                             │    │
│  │  ( ) Débito automático                             │    │
│  │  ( ) Boleto bancário                               │    │
│  │                                                     │    │
│  │  ─────────────────────────────────────────────      │    │
│  │  Resumo:                                            │    │
│  │  Claro Fibra 500MB: R$ 99,90/mês                    │    │
│  │  Taxa de instalação: Grátis                         │    │
│  │  Primeiro mês: R$ 99,90                             │    │
│  │                                                     │    │
│  │         [Finalizar Contratação]                     │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   CONFIRMAÇÃO                               │
│  ┌─────────────────────────────────────────────────────┐    │
│  │                                                     │    │
│  │              ✓ Contratação realizada!               │    │
│  │                                                     │    │
│  │  Protocolo: #CLR-2024-123456                        │    │
│  │                                                     │    │
│  │  Próximos passos:                                   │    │
│  │  1. Você receberá um email de confirmação          │    │
│  │  2. A Claro entrará em contato em 24h              │    │
│  │  3. Instalação agendada para os próximos 5 dias    │    │
│  │                                                     │    │
│  │  [Acompanhar pedido]  [Voltar ao início]            │    │
│  │                                                     │    │
│  └─────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────┘
```

---

## 5. Modelo de Negócio e Monetização

### 5.1 Fontes de Receita

| Fonte | Descrição | % Estimada |
|-------|-----------|------------|
| **Comissão por Contratação** | % sobre cada contrato fechado via app | 60% |
| **Leads Qualificados** | Venda de leads para parceiros | 20% |
| **Assinatura Premium** | Funcionalidades avançadas para usuários | 10% |
| **Publicidade Contextual** | Anúncios relevantes e não intrusivos | 10% |

### 5.2 Detalhamento de Comissões

| Categoria | Comissão Média | Exemplo |
|-----------|---------------|---------|
| Cartões de Crédito | R$ 50-150 por aprovação | Nubank paga ~R$ 80 |
| Seguros | 10-20% do prêmio anual | Seguro R$ 2.000 = R$ 200-400 |
| Planos Telecom | R$ 30-80 por ativação | Plano R$ 100 = R$ 50 |
| Empréstimos | 1-3% do valor contratado | Empréstimo R$ 10k = R$ 100-300 |
| Contas Digitais | R$ 20-50 por abertura | Conta nova = R$ 30 |

### 5.3 Plano Premium (Assinatura)

**Preço Sugerido:** R$ 9,90/mês ou R$ 99,90/ano

**Benefícios:**
- Alertas ilimitados
- Comparações detalhadas com histórico de preços
- Suporte prioritário via chat
- Cashback extra em contratações
- Relatório mensal de economia personalizado
- Sem anúncios

### 5.4 Projeção Financeira (Cenário Base)

| Métrica | Ano 1 | Ano 2 | Ano 3 |
|---------|-------|-------|-------|
| Usuários Ativos | 50.000 | 200.000 | 500.000 |
| Conversão para Contratação | 5% | 7% | 10% |
| Ticket Médio Comissão | R$ 60 | R$ 70 | R$ 80 |
| Receita Comissões | R$ 150k | R$ 980k | R$ 4M |
| Assinantes Premium (5%) | 2.500 | 10.000 | 25.000 |
| Receita Premium | R$ 250k | R$ 1M | R$ 2,5M |
| **Receita Total** | **R$ 400k** | **R$ 2M** | **R$ 6,5M** |

---

## 6. Estratégia de Parcerias e Integrações

### 6.1 Tipos de Parceiros

**Nível 1 - Integração API Completa:**
- Dados em tempo real
- Contratação direta
- Comissão premium
- Parceiros: Grandes bancos, telecom, seguradoras

**Nível 2 - Integração via Afiliados:**
- Link de afiliado
- Redirecionamento para site do parceiro
- Comissão padrão
- Parceiros: Médias empresas, fintechs

**Nível 3 - Dados Públicos/Scraping:**
- Coleta automatizada (respeitando ToS)
- Sem contratação direta
- Comparação apenas
- Usado para aumentar cobertura

### 6.2 Integrações Prioritárias

| Categoria | Parceiros Alvo | Prioridade |
|-----------|---------------|------------|
| Bancos/Fintechs | Nubank, Inter, C6, Itaú, Bradesco | Alta |
| Telecom | Claro, Vivo, Tim, Oi | Alta |
| Seguros | Porto Seguro, Azul, SulAmérica, Youse | Alta |
| Streaming | Netflix, Spotify, Amazon, Disney+ | Média |
| Energia | Enel, CPFL, Light, Cemig | Média |
| Viagens | 123Milhas, Decolar, MaxMilhas | Baixa |

### 6.3 Open Banking/Open Finance

**Oportunidades:**
- Importar automaticamente serviços contratados do usuário
- Analisar gastos por categoria
- Sugerir trocas baseadas em dados reais de consumo
- Integração com PIX para pagamentos

**Requisitos:**
- Certificação junto ao Banco Central
- Compliance com LGPD
- Infraestrutura de segurança

---

## 7. Segurança e Compliance

### 7.1 LGPD (Lei Geral de Proteção de Dados)

**Requisitos Implementados:**
- Consentimento explícito para coleta de dados
- Política de privacidade clara e acessível
- Opção de exclusão de dados (direito ao esquecimento)
- Minimização de dados coletados
- Criptografia de dados sensíveis
- DPO (Data Protection Officer) designado

### 7.2 Segurança da Aplicação

| Camada | Medida | Implementação |
|--------|--------|---------------|
| **Transporte** | TLS 1.3 | HTTPS obrigatório |
| **Autenticação** | JWT + Refresh Tokens | Tokens curtos, renovação segura |
| **Dados** | AES-256 | Dados sensíveis criptografados |
| **API** | Rate Limiting | Proteção contra DDoS |
| **Código** | SAST/DAST | Análise de vulnerabilidades |
| **Infraestrutura** | WAF | Firewall de aplicação |

### 7.3 PCI-DSS (para pagamentos)

- Não armazenar dados de cartão diretamente
- Usar tokenização via gateway certificado
- Auditorias periódicas de segurança

---

## 8. Roadmap de Desenvolvimento

### Fase 1: MVP (3-4 meses)
- [ ] Cadastro e autenticação de usuários
- [ ] Comparação de 2 categorias (Telecom + Bancos)
- [ ] Integração com 3-5 parceiros iniciais
- [ ] Sistema básico de recomendação
- [ ] Contratação via link de afiliado
- [ ] App web responsivo (PWA)

### Fase 2: Expansão (4-6 meses)
- [ ] Apps nativos iOS e Android
- [ ] Adicionar categorias: Seguros, Streaming, Energia
- [ ] Sistema de alertas por push
- [ ] Avaliações e reviews de usuários
- [ ] Contratação integrada (primeiros parceiros)
- [ ] Dashboard de economia

### Fase 3: Inteligência (6-9 meses)
- [ ] Motor de IA para recomendações personalizadas
- [ ] Integração Open Banking
- [ ] Histórico de preços e tendências
- [ ] Comparador de produtos físicos (e-commerce)
- [ ] Programa de cashback

### Fase 4: Escala (9-12 meses)
- [ ] Expansão de parcerias (50+ parceiros)
- [ ] Internacionalização (LATAM)
- [ ] API pública para parceiros B2B
- [ ] White-label para empresas
- [ ] Assistente virtual (chatbot) com IA

---

## 9. Métricas e KPIs

### 9.1 Métricas de Produto

| Métrica | Descrição | Meta Ano 1 |
|---------|-----------|------------|
| **MAU** | Usuários ativos mensais | 50.000 |
| **DAU/MAU** | Stickiness | 25% |
| **Sessão Média** | Tempo no app | 5 min |
| **Comparações/Usuário** | Engajamento | 3/mês |
| **Taxa de Conversão** | Comparações → Contratações | 5% |

### 9.2 Métricas de Negócio

| Métrica | Descrição | Meta Ano 1 |
|---------|-----------|------------|
| **CAC** | Custo de aquisição por cliente | R$ 15 |
| **LTV** | Valor lifetime do cliente | R$ 150 |
| **LTV/CAC** | Eficiência | 10x |
| **MRR** | Receita recorrente mensal | R$ 35k |
| **Churn** | Taxa de cancelamento | < 5% |

### 9.3 Métricas de Qualidade

| Métrica | Descrição | Meta |
|---------|-----------|------|
| **NPS** | Net Promoter Score | > 50 |
| **App Store Rating** | Avaliação nas lojas | > 4.5 |
| **Tempo de Resposta** | Suporte ao cliente | < 2h |
| **Uptime** | Disponibilidade | 99.9% |

---

## 10. Equipe Necessária

### 10.1 Time Inicial (MVP)

| Função | Quantidade | Responsabilidades |
|--------|------------|-------------------|
| **Tech Lead / CTO** | 1 | Arquitetura, decisões técnicas |
| **Full-Stack Developer** | 2 | Desenvolvimento web e API |
| **Mobile Developer** | 1 | Apps iOS/Android |
| **UI/UX Designer** | 1 | Design, protótipos, UX |
| **Product Manager** | 1 | Roadmap, priorização |
| **Growth/Marketing** | 1 | Aquisição, parcerias |

**Total: 7 pessoas**

### 10.2 Time de Escala (Ano 2+)

| Área | Quantidade |
|------|------------|
| Engenharia | 8-12 |
| Produto/Design | 3-4 |
| Dados/ML | 2-3 |
| Growth/Marketing | 4-5 |
| Comercial/Parcerias | 3-4 |
| Operações/CS | 3-4 |

**Total: 23-32 pessoas**

---

## 11. Investimento Inicial Estimado

### 11.1 Custos de Desenvolvimento (MVP)

| Item | Custo Mensal | 4 Meses |
|------|-------------|---------|
| Equipe (7 pessoas) | R$ 70.000 | R$ 280.000 |
| Infraestrutura Cloud | R$ 3.000 | R$ 12.000 |
| Ferramentas/SaaS | R$ 2.000 | R$ 8.000 |
| Design/Protótipos | R$ 5.000 | R$ 20.000 |
| Legal/Contábil | R$ 3.000 | R$ 12.000 |
| **Total MVP** | | **R$ 332.000** |

### 11.2 Custos de Lançamento

| Item | Custo |
|------|-------|
| Marketing de lançamento | R$ 50.000 |
| Certificações/Licenças | R$ 20.000 |
| Reserva operacional (3 meses) | R$ 150.000 |
| **Total Lançamento** | **R$ 220.000** |

### 11.3 Investimento Total Recomendado

| Fase | Valor |
|------|-------|
| MVP + Lançamento | R$ 550.000 |
| Buffer de segurança (20%) | R$ 110.000 |
| **Total** | **R$ 660.000** |

---

## 12. Riscos e Mitigações

| Risco | Probabilidade | Impacto | Mitigação |
|-------|--------------|---------|-----------|
| Dificuldade em fechar parcerias | Alta | Alto | Começar com afiliados, provar valor |
| Concorrência de players estabelecidos | Média | Alto | Diferenciação por IA e UX |
| Regulamentação restritiva | Baixa | Alto | Compliance desde o início |
| Baixa adoção de usuários | Média | Alto | Testes de produto, pivots rápidos |
| Problemas de escalabilidade | Baixa | Médio | Arquitetura cloud-native |
| Vazamento de dados | Baixa | Crítico | Segurança by design, auditorias |

---

## 13. Próximos Passos

### Imediato (Semana 1-2)
1. [ ] Validar conceito com potenciais usuários (entrevistas)
2. [ ] Pesquisar concorrentes em profundidade
3. [ ] Definir 2-3 parceiros prioritários para contato inicial
4. [ ] Criar wireframes detalhados das principais telas
5. [ ] Definir stack tecnológico final

### Curto Prazo (Mês 1)
1. [ ] Desenvolver protótipo navegável (Figma)
2. [ ] Iniciar conversas com parceiros potenciais
3. [ ] Configurar ambiente de desenvolvimento
4. [ ] Definir estrutura societária e jurídica
5. [ ] Buscar investimento seed (se necessário)

### Médio Prazo (Mês 2-4)
1. [ ] Desenvolver MVP completo
2. [ ] Integrar primeiros parceiros
3. [ ] Testes beta com usuários reais
4. [ ] Ajustes baseados em feedback
5. [ ] Preparar lançamento

---

## 14. Conclusão

O **ComparaAí** tem potencial para se tornar o principal comparador inteligente do Brasil, preenchendo uma lacuna de mercado significativa. O diferencial de multi-verticalidade, personalização via IA e contratação integrada cria uma proposta de valor única.

**Fatores Críticos de Sucesso:**
1. Qualidade e atualização dos dados
2. UX excepcional e simples
3. Parcerias sólidas com fornecedores
4. Recomendações realmente personalizadas
5. Confiança do usuário (transparência)

**Recomendação:** Iniciar com MVP focado em 2 verticais (Telecom + Bancos), validar product-market fit, e expandir gradualmente.

---

*Documento criado em: Dezembro 2024*
*Versão: 1.0*
*Status: Pronto para revisão e aprovação*
