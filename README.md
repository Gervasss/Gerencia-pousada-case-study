# 🏨 Caso de Estudo: Sistema de Gerenciamento de Pousada

Este repositório documenta o desenvolvimento do sistema **Gerência Pousada**, uma solução Full Stack projetada para centralizar a gestão operacional, desde o controle de hóspedes até o gerenciamento estratégico de estoque e reservas.

> **Nota:** O código-fonte original deste projeto é privado. Este documento detalha a arquitetura, funcionalidades e o impacto da solução no dia a dia operacional.

---

## 📝 Visão Geral do Projeto

O objetivo central foi otimizar a gestão de hospedagem, reduzindo falhas manuais e garantindo a integridade dos dados. O sistema oferece uma visão consolidada de todas as áreas críticas de uma pousada em uma interface única e intuitiva.

## 🛠️ Tecnologias Utilizadas

* **Frontend:** React + Vite com TypeScript (foco em segurança e previsibilidade do código).
* **Estilização:** Styled Components e CSS (interface moderna e responsiva).
* **Backend:** Python com Django.
* **Banco de Dados:** SQLite (garantindo integridade relacional ).

---

## 💡 Minha Atuação e Responsabilidades

Fui o **responsável exclusivo por todo o desenvolvimento do Frontend** da aplicação. Minha atuação incluiu:
* Implementação das **regras de negócio complexas** relacionadas ao gerenciamento de reservas.
* Definição de fluxos de navegação, validações de formulários e interações entre telas.
* Integração completa com o Backend via API para assegurar a consistência dos dados em tempo real.

---

## 🏗️ Estrutura Funcional (Módulos)

### 👥 Módulo de Hóspedes
* Cadastro completo e pesquisa rápida de clientes.
* Integração direta: permite cadastrar novos hóspedes sem sair da tela de criação de reserva, evitando duplicidade e otimizando o fluxo.

### 📦 Módulo de Estoque
* Controle detalhado por categorias (Recepção, Cozinha, Quartos).
* Registro de baixas e reposições via modais específicos.
* Integração com o consumo do hóspede: itens retirados do frigobar são descontados automaticamente do estoque geral.

### 🛏️ Módulo de Quartos
* Visualização da ocupação atual e futura.
* **Validação Anti-Conflito:** O sistema impede tecnicamente a criação de reservas em datas coincidentes para o mesmo quarto, eliminando o erro de *overbooking*.

### 📅 Módulo de Reservas (Núcleo do Sistema)
* Cálculo automático de diárias com base no perfil da reserva (quantidade de pessoas, presença de crianças).
* **Gestão de Consumo:** Modal para registro de consumo em tempo real, somando valores automaticamente ao total da hospedagem para um fechamento de conta ágil e transparente.

### 📊 Módulo de Relatórios
* Listagem completa de reservas com filtros por intervalos de datas.
* Fornece dados atualizados para planejamento operacional e análise de desempenho do estabelecimento.

---

## 📂 Estrutura do Frontend (Minha Atuação)

Como responsável pelo desenvolvimento do frontend, estruturei o projeto para facilitar a integração e manutenção:

```text
src/
├── assets/          # Recursos visuais e ícones
├── components/      # Componentes reutilizáveis (Modais, Inputs, Cards)
├── pages/           # Telas (Hóspedes, Reservas, Estoque, Quartos, Relatórios)
├── services/        # Integração com a API Django
├── styles/          # Temas globais e Styled Components
├── types/           # Interfaces TypeScript (Reservas, Hóspedes, Produtos)
└── utils/           # Validadores e formatadores (Datas, Moeda)

---
```


---

### 📂 Estrutura do Backend (Django)

A arquitetura do backend segue o padrão **MVT (Model-View-Template)** do Django, organizada de forma modular para garantir que cada funcionalidade da pousada tenha sua própria responsabilidade e isolamento de lógica.

```text
backend/
├── inventory/          # Gestão de estoque e controle de insumos
├── payments/           # Processamento de faturamentos e transações financeiras
├── pousada_backend/    # Configurações globais do projeto (settings, urls, wsgi)
├── reservations/       # Núcleo do sistema: regras de negócio e calendários
├── rooms/              # Gerenciamento de quartos e controle de disponibilidade
├── users/              # Autenticação, perfis de hóspedes e administradores
├── db.sqlite3          # Banco de dados local utilizado no desenvolvimento
├── manage.py           # Utilitário de linha de comando principal do Django
├── requirements.txt    # Lista de dependências e bibliotecas Python do projeto
└── notes.txt           # Documentação técnica interna e rascunhos

```

### 🛠️ Detalhes dos Módulos

* **inventory**: Implementa o controle detalhado de produtos, permitindo baixas automáticas baseadas no consumo registrado.
* **reservations**: Centraliza as principais regras de negócio, integrando hóspedes, quartos e períodos de estadia sem conflitos.
* **rooms**: Aplica as validações que impedem reservas duplicadas para o mesmo quarto em datas coincidentes.
* **users**: Gerencia o cadastro completo de hóspedes e o histórico de estadias para futuras consultas.

---

## ⚙️ Como Rodar o Projeto (Ambiente de Desenvolvimento)

### 1. Pré-requisitos
* Node.js e NPM/Yarn.
* Python 3.x e ambiente virtual (venv).
* SQLite instalado.

### 2. Configuração do Backend (Django)
```bash
# Entrar na pasta do backend e instalar dependências
pip install -r requirements.txt

# Configurar o banco de dados no settings.py e rodar migrations
python manage.py migrate

# Iniciar o servidor
python manage.py runserver

```

### 3. Configuração do Frontend (React + Vite)

```bash
# Instalar dependências
npm install

# Iniciar o ambiente de desenvolvimento
npm run dev

```

---

## 📈 Resultados e Impacto

* **Zero Conflitos:** A automação eliminou erros de duplicidade em reservas.


* **Eficiência Financeira:** Cálculos automáticos de consumo e diárias reduziram o tempo de checkout e evitaram divergências com clientes.


* **Confiabilidade:** A centralização dos dados permitiu uma gestão interna alinhada às necessidades reais do dia a dia da pousada.



---

**Desenvolvido por Gervásio Cardoso** [LinkedIn](https://www.google.com/search?q=https://www.linkedin.com/in/gerv%C3%A1sio-cardoso/) | [GitHub](https://www.google.com/search?q=https://github.com/Gervasss)

## 📸 Demonstração 


Painel:

<img width="886" height="423" alt="image" src="https://github.com/user-attachments/assets/98ef2733-b02d-4ab3-a84b-b6d7eedd319f" />

Aba de Hóspedes:

<img width="886" height="424" alt="image" src="https://github.com/user-attachments/assets/68c3a896-0be4-4b69-a542-5ab9e3848684" />

Aba de Estoque:

<img width="886" height="421" alt="image" src="https://github.com/user-attachments/assets/0f914434-5943-4001-8183-842cfca62e7c" />


<img width="886" height="426" alt="image" src="https://github.com/user-attachments/assets/f2b299f3-cc43-4023-a2fd-20371b3a066f" />


Aba de Quartos:

<img width="886" height="426" alt="image" src="https://github.com/user-attachments/assets/03a856a6-e0d0-4714-ab30-c6a1178b554c" />


<img width="886" height="426" alt="image" src="https://github.com/user-attachments/assets/7984656d-a13d-4501-9cfc-6b4dc2771896" />


Aba de Reservas:

<img width="886" height="417" alt="image" src="https://github.com/user-attachments/assets/d185887a-4934-4d99-8c92-2dce045a50b4" />

<img width="886" height="423" alt="image" src="https://github.com/user-attachments/assets/f2c3b7fd-3d37-49c7-8c2a-e47f26290159" />


Aba de Relatórios:

<img width="886" height="423" alt="image" src="https://github.com/user-attachments/assets/eb1b5841-7b7e-4ed7-8784-f050686ccb19" />






