---
title: Disponibilidade do aplicativo aprovações no Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Saiba mais sobre a disponibilidade do aplicativo Aprovações no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909515"
---
# <a name="teams-approvals-app-availability"></a>Disponibilidade do aplicativo Aprovações do Teams

O aplicativo Aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.
O aplicativo Aprovações fornece uma maneira simples de trazer auditoria, conformidade, responsabilidade e fluxos de trabalho para aprovações estruturadas e não estruturadas no Teams.

 ![mostra o aplicativo aprovações](media/approvals-selection.png)

Os usuários podem fixar o aplicativo Aprovações para salvá-lo na barra de menus.

 ![mostra o aplicativo aprovações com a opção fixar](media/approvalApp-pin.png)

A primeira aprovação criada a partir do aplicativo Aprovações acionará o provisionamento da Solução de Aprovação no ambiente de CDS (Common Data Service) padrão. As aprovações criadas a partir do aplicativo Aprovações serão armazenadas no ambiente de CDS padrão.

Este artigo descreve os requisitos e funções do aplicativo Aprovações.

## <a name="required-permissions-and-licenses"></a>Permissões e licenças necessárias

Para usar o aplicativo Aprovações, você precisa de permissão para os seguintes itens:

- Permissões para criar um banco de dados de CDS da Microsoft.

- Uma conta na [flow.microsoft.com](https://flow.microsoft.com/)

- Função de administrador no ambiente de destino.

- Licença para [um Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)um Office 365 ou um Dynamics 365.

## <a name="storage-with-cds"></a>Armazenamento com CDS

O MODELO de Dados Comuns (CDM) é a linguagem de dados compartilhada usada por aplicativos comerciais e analíticos no CDS. Ele consiste em um conjunto de esquemas de dados padronizados e extensíveis publicados pela Microsoft e por nossos parceiros que permite a consistência dos dados e seu significado entre aplicativos e processos de negócios. Saiba mais sobre o [Modelo de Dados Comuns da Plataforma Microsoft Power.](https://docs.microsoft.com/power-automate/get-started-approvals)

Saiba mais sobre o fluxo [de trabalho Aprovação.](https://docs.microsoft.com/power-automate/modern-approvals)

## <a name="approvals-teams-app-permissions"></a>Permissões do aplicativo Aprovações do Teams

O aplicativo Aprovações do Teams permite que você acesse os seguintes recursos:

- Receba mensagens e dados que você fornecer a eles.

- Enviar mensagens e notificações.

- Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.

- Acesse suas informações de perfil, como seu nome, endereço de email, nome da empresa e idioma preferido.

- Receba mensagens e dados que os membros da equipe fornecem a eles em um canal.

- Enviar mensagens e notificações em um canal.

- Acesse as informações da sua equipe:
  - nome da equipe
  - lista de canais
  - lista (nomes e endereços de email do membro da equipe).

- Use as informações da equipe para contatá-las.

## <a name="disable-the-approvals-app"></a>Desabilitar o aplicativo Aprovações

O aplicativo Aprovações está disponível por padrão. Você pode desabilitar o aplicativo no Centro de administração do Teams.

  1. Entre no Centro de administração do Teams.

  2. Expanda **os aplicativos do Teams** e selecione Gerenciar **aplicativos.**

  3. Pesquise o aplicativo Aprovações.

![mostra a navegação do Centro de administração com os aplicativos do Teams > Gerenciar Aplicativos realçadas](media/manage-approval-apps.png)

  4. Selecione Aprovações.

  5. Selecione o alternância para desabilitar o aplicativo para sua organização.

![mostra os detalhes do aplicativo Aprovações](media/approvals-details.png)

## <a name="retention-policy"></a>Política de retenção

As aprovações criadas a partir do aplicativo Aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento. Saiba mais sobre como [fazer backup e restaurar ambientes – Power Platform Microsoft \| Docs.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)

## <a name="auditing"></a>Auditoria

O aplicativo Aprovações registra eventos de auditoria no Centro de Conformidade e Segurança do Microsoft 365. Você pode exibir o log de auditoria.

1. Vá para o Site de Conformidade do Microsoft 365.

2. Selecione a **seção Auditoria.**

3. Pesquise atividades nas **atividades de aprovação do Microsoft Teams.**

Você pode procurar as seguintes atividades:

- Criar nova solicitação de aprovação

- Exibir detalhes da solicitação de aprovação

- Solicitação de aprovação aprovada

- Solicitação de aprovação rejeitada

- Solicitação de aprovação cancelada

- Solicitação de aprovação compartilhada

- Arquivo anexado à solicitação de aprovação

- Solicitação de aprovação reatribuida

- Assinatura eletrônica adicionada à solicitação de aprovação

Para obter acesso a mais aprovações de auditoria no Flow, habilita e configure a auditoria no ambiente padrão para as entidades de aprovação principal Aprovação, Solicitação de Aprovação e Resposta de Aprovação. As operações criar, atualizar e excluir são eventos auditáveis para registros de Aprovação. Saiba mais sobre a auditoria de dados e a atividade do usuário para segurança e [conformidade – Power Platform Microsoft \| Docs.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)

A auditoria pode ser personalizada ainda mais no Centro de Conformidade e Segurança do [Microsoft 365.](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)

1. Para usar os relatórios pré-configurados, entre no Microsoft 365 Security and Compliance.

2. Selecione **Pesquisar & investigação.**

3. Pesquise o log de auditoria e selecione a guia de atividades **do Dynamics 365.**

Saiba mais sobre o registro em log de atividades de aplicativos do [Microsoft Dataverse](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)e de aplicativos orientados por modelo – Power Platform.

## <a name="security"></a>Segurança

A partir do aplicativo Aprovações do Teams, os usuários têm acesso para criar novas Aprovações e exibir Aprovações que eles enviaram e receberam. Os usuários não terão acesso às Aprovações criadas por outras pessoas, a menos que sejam um respondente ou um visualizador da solicitação.

> [!Note]
> Um usuário receberá uma função de visualizador de uma solicitação se ele faz parte do chat ou canal em que a aprovação foi criada. Eles não terão a capacidade de tomar medidas na solicitação se não receberam essa função quando a aprovação foi criada.
