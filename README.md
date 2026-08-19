# 📝 React Forms

Projeto desenvolvido durante a **Formação Full Stack da Rocketseat**, com foco no desenvolvimento e validação de formulários utilizando **React, TypeScript, React Hook Form e Yup**.

> **Contexto:** a estrutura inicial do projeto e os demais arquivos foram fornecidos pelo professor. O foco deste exercício foi a implementação da lógica do formulário no `App.tsx`.

## 🎯 Objetivo

Praticar a criação de formulários em React utilizando uma abordagem estruturada para:

- Gerenciar os valores dos campos.
- Tipar os dados com TypeScript.
- Validar informações antes do envio.
- Exibir mensagens de erro.
- Integrar React Hook Form com Yup.
- Utilizar `Controller` para diferentes tipos de campos.
- Processar os dados enviados pelo formulário.

 ---

<img width="1076" height="1771" alt="Captura_de_tela_20260817_161016" src="https://github.com/user-attachments/assets/9de0b832-bb4a-4ce7-ba31-45bf83208277" />

 ---

## 📝 Formulário

O projeto possui um formulário para cadastro de um evento.

### Campos

- **Nome do evento**
- **Data**
- **Assunto**
- **Descrição**

### Assuntos disponíveis

- React
- Node.js
- Javascript
- Typescript

## ⚛️ Tecnologias utilizadas

- **React 18**
- **TypeScript**
- **React Hook Form**
- **Yup**
- **@hookform/resolvers**
- **Vite**
- **ESLint**

## 🧠 Principais conceitos praticados

### TypeScript

Os dados do formulário foram tipados através de:

```ts
type FormData = {
  name: string;
  date: string;
  subject: string;
  description: string;
};
```

### React Hook Form

O gerenciamento do formulário utiliza `useForm`:

```tsx
const {
  control,
  handleSubmit,
  formState: { errors },
} = useForm<FormData>({
  defaultValues: {
    name: "",
    date: "",
    subject: "",
    description: "",
  },
  resolver: yupResolver(schema),
});
```

### Controller

Os campos foram integrados ao React Hook Form através do `Controller`, incluindo:

- `input`
- `input type="date"`
- `select`
- `textarea`

Exemplo:

```tsx
<Controller
  control={control}
  name="name"
  render={({ field }) => (
    <input type="text" placeholder="Nome do evento" {...field} />
  )}
/>
```

## ✅ Validação com Yup

As regras de validação foram definidas com Yup:

```ts
const schema = yup.object({
  name: yup.string().required("Nome é obrigatório"),
  date: yup.string().required("Data é obrigatória"),
  subject: yup.string().required("Selecione um assunto"),
  description: yup
    .string()
    .required("Descrição é obrigatória")
    .min(10, "A descrição precisa ter pelo menos 10 caracteres"),
});
```

### Regras

| Campo | Regra |
|---|---|
| Nome | Obrigatório |
| Data | Obrigatória |
| Assunto | Obrigatório |
| Descrição | Obrigatória |
| Descrição | Mínimo de 10 caracteres |

A integração entre Yup e React Hook Form é feita com:

```tsx
resolver: yupResolver(schema)
```

## 🚨 Tratamento de erros

Os erros são obtidos através de `formState.errors` e exibidos individualmente:

```tsx
{errors.name?.message && (
  <span className="error">{errors.name.message}</span>
)}
```

O mesmo padrão é utilizado para os campos de data, assunto e descrição.

## 📤 Envio do formulário

O envio é controlado pelo `handleSubmit`:

```tsx
<form onSubmit={handleSubmit(onSubmit)}>
```

Os dados são recebidos pela função:

```tsx
function onSubmit(data: FormData) {
  console.log(data);
}
```

Neste exercício, os dados enviados são exibidos no console do navegador.

## 🎨 Estilização

O projeto utiliza CSS para estilização do formulário, incluindo:

- Centralização da interface.
- Organização vertical dos campos.
- Espaçamento entre elementos.
- Estilização de `input`, `select` e `textarea`.
- Estilização do botão.
- Personalização do campo de data.
- Ícones para calendário e seleção.
- Mensagens de erro.
- Fonte Poppins.

> A estrutura de estilos foi fornecida como parte da base do exercício. O foco da implementação realizada esteve no `App.tsx`.

## 📚 O que eu aprendi

Este projeto foi mais uma etapa importante na minha evolução com React.

O principal aprendizado foi entender como trabalhar com **formulários de maneira estruturada**, utilizando bibliotecas específicas para gerenciamento e validação.

Durante o exercício, pratiquei:

- Tipagem de formulários com TypeScript.
- Gerenciamento de formulários com React Hook Form.
- Utilização do `useForm`.
- Configuração de `defaultValues`.
- Utilização do `Controller`.
- Criação de schemas de validação com Yup.
- Integração entre Yup e React Hook Form.
- Utilização do `yupResolver`.
- Tratamento de erros com `formState.errors`.
- Validação de campos obrigatórios.
- Validação de tamanho mínimo.
- Processamento do envio do formulário.

## 🏗️ Escopo do exercício

Este projeto faz parte de uma atividade prática da **Formação Full Stack da Rocketseat**.

A estrutura inicial da aplicação foi disponibilizada pelo professor.

### Implementação realizada

O foco do meu desenvolvimento foi o arquivo:

```text
src/
└── App.tsx
```

Neste arquivo foram implementados:

- Tipagem dos dados.
- Schema de validação.
- Configuração do React Hook Form.
- Integração com Yup.
- Controllers dos campos.
- Tratamento das mensagens de erro.
- Função de submissão do formulário.

Isso permitiu concentrar o aprendizado nos conceitos de **formulários, validação e gerenciamento de dados no React**.

## 🚀 Como executar

### 1. Clone o repositório

```bash
git clone https://github.com/abdallahleandro/React-Forms
```

### 2. Acesse a pasta

```bash
cd react-forms
```

### 3. Instale as dependências

```bash
npm install
```

### 4. Execute o projeto

```bash
npm run dev
```

O Vite disponibilizará a aplicação em um endereço local indicado no terminal.

## 📦 Scripts disponíveis

| Comando | Descrição |
|---|---|
| `npm run dev` | Inicia o ambiente de desenvolvimento |
| `npm run build` | Gera o build de produção |
| `npm run lint` | Executa o ESLint |
| `npm run preview` | Executa uma prévia do build |

## 📁 Estrutura relacionada à implementação

```text
src/
├── App.tsx
└── App.css
```

> A estrutura completa do projeto contém outros arquivos fornecidos na base do exercício. O foco da implementação realizada foi o `App.tsx`.

## 🎓 Formação

Projeto desenvolvido durante a:

**Formação Full Stack — Rocketseat**

## 👨‍💻 Autor

**Leandro Abdallah**

Profissional de TI com mais de 14 anos de experiência em suporte técnico, atualmente direcionando sua carreira para o desenvolvimento de software.

### Tecnologias em evolução

`Node.js` `TypeScript` `React` `JavaScript` `APIs REST` `PostgreSQL` `Prisma` `Docker`

---

⭐ Mais um projeto concluído. Mais um conceito aprendido. Seguimos evoluindo.
