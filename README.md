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

### 📊 Módulo de Relatórios de Reservas
O módulo de relatórios foi desenvolvido para fornecer ao administrador uma visão clara e analítica do desempenho da pousada. Ele consolida dados de faturamento e ocupação, permitindo decisões baseadas em dados.

Principais Funcionalidades:
Indicadores de Desempenho (KPIs):

* Total de Reservas: Monitoramento da quantidade de reservas efetuadas no período selecionado.

* Receita no Período: Visualização imediata do faturamento bruto.

* Ticket Médio: Cálculo automático do valor médio gasto por reserva, auxiliando na análise de rentabilidade.

* Filtros Inteligentes: Possibilidade de filtrar o histórico por Mês e Ano, além de uma barra de busca para localizar hóspedes ou quartos específicos rapidamente.

* Listagem Detalhada: Tabela organizada contendo ID da reserva, nome do hóspede, número do quarto, datas de check-in/out, status do pagamento e valor total.

* Exportação de Dados: Botão para Exportar em PDF, facilitando o arquivamento offline ou compartilhamento dos dados com a contabilidade.

Tecnologias e Conceitos Aplicados:
* Data Visualization: Uso de cards destacados para métricas essenciais.

* UX Design: Interface limpa com uso de cores para indicar status (ex: verde para reservas confirmadas).

* Gestão de Estado: Manipulação dinâmica da tabela conforme os filtros aplicados.

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

<img width="886" height="475" alt="image" src="https://github.com/user-attachments/assets/8d331591-40c8-4965-9a83-253c5a5bf9dd" />



Aba de Hóspedes:

<img width="886" height="474" alt="image" src="https://github.com/user-attachments/assets/0523ba9a-abff-4492-9661-296c37224dc3" />



Aba de Estoque:

<img width="886" height="474" alt="image" src="https://github.com/user-attachments/assets/a8ed3423-f1d5-46ab-ab02-8a30767f8d2f" />


<img width="886" height="474" alt="image" src="https://github.com/user-attachments/assets/ab59242c-361a-4fce-9be7-4dffca6d0ed0" />




Aba de Quartos:

<img width="886" height="472" alt="image" src="https://github.com/user-attachments/assets/6b943a8d-7ca2-4fdc-b433-48304fd41055" />

<img width="886" height="475" alt="image" src="https://github.com/user-attachments/assets/5ac3074a-19a7-4919-9d34-8c699cac1735" />



Aba de Reservas:

<img width="886" height="475" alt="image" src="https://github.com/user-attachments/assets/b5b50ca7-b3ec-4078-a40b-7413b702c0a8" />


<img width="886" height="420" alt="image" src="https://github.com/user-attachments/assets/6a8d0b1b-5de1-4b00-bee4-4101cebe547f" />



Aba de Relatórios:
<img width="886" height="476" alt="image" src="https://github.com/user-attachments/assets/62cd5a25-3cd1-4492-b548-a139a2c67146" />


<img width="886" height="950" alt="image" src="https://github.com/user-attachments/assets/c759880d-bc92-40c1-b36c-88d7cc7d9f65" />








