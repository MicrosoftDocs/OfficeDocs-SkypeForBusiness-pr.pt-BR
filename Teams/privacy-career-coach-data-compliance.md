---
title: Informações de conformidade e dados do Career Coach
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ''
search.appverid: MET150
f1keywords: ''
description: Aprenda as medidas de privacidade, conformidade e purview tomadas pela Microsoft em relação à Educação ou ao Coach de Carreira da EDU.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 0f28381aad61cbe7fecf21e189bc5ab278ce3008
ms.sourcegitcommit: 9ea1ed450ba89e9cbc094018a832bd25c08e92e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68825676"
---
# <a name="career-coach-data-and-compliance"></a>Dados e conformidade do Career Coach

Este artigo discute como usar a funcionalidade no aplicativo, bem como outras ferramentas para ajudá-lo a encontrar e agir sobre dados pessoais ou informações pessoais para responder a DSRs (Solicitação de Assunto de Dados) em conformidade com suas obrigações de RGPD. O Career Coach classifica amplamente os dados em duas categorias: conteúdo do cliente e logs gerados pelo sistema. No Career Coach, o conteúdo do cliente inclui dados de usuário, dados de configuração de locatário e dados de atividade do aluno, enquanto os logs gerados pelo sistema incluem logs e dados relacionados gerados pela Microsoft que ajudam a Microsoft a fornecer serviços corporativos aos usuários.

## <a name="customer-content"></a>Conteúdo do cliente

### <a name="user-data"></a>Dados do usuário

Os dados de usuário coletados pelo Career Coach incluem informações de perfil, como metas e progresso de atividades, campo de estudo, ano na escola, habilidades salvas, carreiras salvas, currículos carregados e transcrições.

#### <a name="deleting-user-data"></a>Excluindo dados do usuário

Siga estas etapas para excluir dados do usuário do Career Coach:

1. Um administrador global deve [abrir um tíquete](https://edusupport.microsoft.com/support?product_id=career_coach) de suporte que declare claramente a solicitação de uma operação de DSR de exclusão de GDPR (solicitações de assunto de dados). ** Não há capacidade de limitar o conjunto de dados ou a janela de tempo da exclusão**.
2. A solicitação deve declarar claramente o tipo de dados que precisa ser excluído:
    1. Todos os dados do usuário para o locatário.
    2. Dados do usuário para um usuário específico. Inclua o OID do usuário (identificadores de objeto) como parte da solicitação de exclusão.
3. Depois de arquivado, o tíquete de suporte será abordado após uma semana para atender à política de retenção mínima da conformidade. Você pode cancelar a operação durante esse tempo.
4. Após uma semana, a equipe do Career Coach exclui todos os dados relacionados ao locatário. O suporte da Microsoft monitora o tíquete e notificará você depois que o processo de exclusão for concluído **, em no máximo 30 dias**.

#### <a name="exporting-user-data"></a>Exportando dados de usuário

Siga estas etapas para exportar dados de usuário do Career Coach:

1. [Open Career Coach](https://aka.ms/Career_Coach_App)  e exibir seu perfil.
1. Role até a seção privacidade e segurança.
1. Selecione "Baixar" para exportar todos os dados do cliente para sua conta.

### <a name="tenant-configuration-data"></a>Dados de configuração do locatário

Os dados do locatário incluem informações carregadas ou geradas como parte da configuração do aplicativo Career Coach. Esses dados incluem informações de marca, logotipo e ícone de aprendizagem de um locatário, catálogo de cursos, URL escolar do LinkedIn, campos da lista de estudos e todos os outros dados adicionados durante a configuração de locatário do Career Coach no centro de administração do Teams.

#### <a name="deleting-tenant-configuration-data"></a>Excluindo dados de configuração de locatário

Siga estas etapas para excluir dados de configuração de locatário do Career Coach:

1. Um administrador global deve [abrir um tíquete de suporte](https://edusupport.microsoft.com/support?product_id=career_coach) informando claramente a solicitação para excluir os dados de configuração do seu locatário.  **Não há capacidade de limitar o conjunto de dados ou a janela de tempo da exclusão**.
1. Depois de arquivado, o tíquete de suporte será abordado após uma semana para atender à política de retenção mínima da conformidade. Você pode cancelar a operação durante esse tempo.
1. Após uma semana, a equipe do Career Coach exclui todos os dados relacionados ao locatário. O suporte da Microsoft monitora o tíquete e notificará você depois que o processo de exclusão for concluído **, em no máximo 30 dias**.

### <a name="student-activity-data"></a>Dados da atividade do aluno

O Career Coach armazena dados de atividade do aluno no mesmo local que  [Insights para Educação](class-insights.md). Os dados agregados são exibidos na experiência de insights de atividade do aluno do Career Coach. Os dados de uso do aluno capturados para alimentar esse recurso são armazenados e retidos por um ano.

#### <a name="deleting-student-activity-data"></a>Excluindo dados de atividade do aluno

Para remover dados de atividade do aluno para um indivíduo ou locatário, siga as etapas em [Como excluir dados do usuário dos insights do Education](class-insights.md#how-to-delete-user-data-from-education-insights).

## <a name="system-generated-logs"></a>Logs gerados pelo sistema

Os logs gerados pelo sistema incluem logs e dados relacionados gerados pela Microsoft que ajudam a Microsoft a fornecer serviços corporativos aos usuários. Os logs gerados pelo sistema contêm principalmente dados pseudonymizados, como identificadores exclusivos (normalmente um número gerado pelo sistema) que não podem identificar uma pessoa individual, mas são usados para fornecer os serviços corporativos aos usuários. Exemplos desses dados incluem:

- Dados de uso do produto e do serviço, como logs de atividades do usuário.
- Solicitações de pesquisa de usuário e dados de consulta.
- Dados gerados por produtos e serviços como um produto da funcionalidade e interação do sistema por usuários ou outros sistemas.

> [!NOTE]
> Não há suporte para a capacidade de restringir ou corrigir dados em logs gerados pelo sistema. Os dados em logs gerados pelo sistema constituem ações factuais realizadas na nuvem e nos dados de diagnóstico da Microsoft, e modificações nesses dados comprometeriam o registro histórico de ações e aumentariam os riscos de fraude e segurança. O Career Coach mantém logs gerados pelo sistema por 30 dias.

### <a name="exporting-and-deleting-system-generated-logs"></a>Exportar e excluir logs gerados pelo sistema

O administrador global do locatário é a única pessoa em sua organização que pode acessar logs gerados pelo sistema associados ao uso de Office 365 serviços e aplicativos de um determinado usuário. O Career Coach se alinha [ao processo de acesso e exportação de logs gerados pelo sistema fornecidos pelo Office 365](https://learn.microsoft.com/compliance/regulatory/gdpr-dsr-Office365#accessing-and-exporting-system-generated-logs).

## <a name="more-information"></a>Mais informações

- [Introdução ao Career Coach para Microsoft Teams](career-coach.md)
- [Perguntas frequentes sobre privacidade](https://privacy.microsoft.com/faq)
- [Produtos da Microsoft e seus dados – Privacidade da Microsoft](https://privacy.microsoft.com/privacy-in-our-products)
- [Configurações de privacidade da conta da Microsoft](https://account.microsoft.com/account/privacy?refd=privacy.microsoft.com&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2F%3Frefd%3Dprivacy.microsoft.com&destrt=privacy-dashboard)
