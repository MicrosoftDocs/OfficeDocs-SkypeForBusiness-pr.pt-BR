---
title: Aprovações na disponibilidade de aplicativos no Teams
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
description: Saiba mais sobre a disponibilidade de aplicativos de aprovação no Microsoft Teams.
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
# <a name="teams-approvals-app-availability"></a>Aprovação do aplicativo aprovações de equipe

O aplicativo aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.
O aplicativo aprovações fornece uma maneira simples de trazer auditoria, conformidade, responsabilidade e fluxos de trabalho para aprovações estruturadas e não estruturadas no Teams.

 ![mostra o aplicativo aprovações](media/approvals-selection.png)

Os usuários podem fixar o aplicativo aprovações para salvá-lo na barra de menus.

 ![mostra o aplicativo aprovações com a opção PIN](media/approvalApp-pin.png)

A primeira aprovação criada a partir do aplicativo aprovações irá disparar o provisionamento da solução de aprovação no ambiente padrão de serviços de dados comuns (CDS). As aprovações criadas do aplicativo aprovações serão armazenadas no ambiente de CDS padrão.

Este artigo descreve os requisitos e funções do aplicativo aprovações.

## <a name="required-permissions-and-licenses"></a>Permissões e licenças necessárias

Para usar o aplicativo aprovações, você precisa de permissão para os seguintes itens:

- Permissões para criar um banco de dados do Microsoft CDS.

- Uma conta no [Flow.Microsoft.com](https://flow.microsoft.com/)

- Função de administrador no ambiente de destino.

- Licença para [automatização de energia](https://docs.microsoft.com/power-automate/get-started-approvals), um Office 365 ou um Dynamics 365.

## <a name="storage-with-cds"></a>Armazenamento com CDS

O modelo de dados comuns (MDL) é o idioma de dados compartilhados usados por aplicativos analíticos e comerciais nos CDS. Ele consiste em um conjunto de esquemas de dados extensíveis e padronizados publicados pela Microsoft e por nossos parceiros que permitem a consistência de dados e seu significado entre aplicativos e processos de negócios. Saiba mais sobre o [modelo de dados comum da plataforma de alimentação da Microsoft](https://docs.microsoft.com/power-automate/get-started-approvals).

Saiba mais sobre o [fluxo de trabalho de aprovação](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Permissões do aplicativo equipes de aprovações

O aplicativo de equipes de aprovação permite que você acesse os seguintes recursos:

- Receba mensagens e dados fornecidos a ele.

- Envie mensagens e notificações para você.

- Renderizar aplicativos pessoais e caixas de diálogo sem um cabeçalho fornecido pelo Teams.

- Acesse suas informações de perfil, como seu nome, endereço de e-mail, nome da empresa e idioma preferencial.

- Receber mensagens e dados que os membros da equipe fornecem a ele em um canal.

- Envie mensagens e notificações em um canal.

- Acesse as informações da sua equipe:
  - nome da equipe
  - lista de canais
  - lista (nomes e endereços de email dos membros da equipe).

- Use as informações da equipe para contatá-los.

## <a name="disable-the-approvals-app"></a>Desabilitar o aplicativo aprovações

O aplicativo aprovações está disponível por padrão. Você pode desabilitar o aplicativo no centro de administração do teams.

  1. Entre no centro de administração do Microsoft Teams.

  2. Expanda **aplicativos do teams** e selecione **gerenciar aplicativos**.

  3. Procure o aplicativo aprovações.

![mostra a navegação do centro de administração com aplicativos do teams > gerenciar aplicativos realçados](media/manage-approval-apps.png)

  4. Selecione aprovações.

  5. Selecione o botão de alternância para desabilitar o aplicativo para a sua organização.

![mostra os detalhes do aplicativo aprovações](media/approvals-details.png)

## <a name="retention-policy"></a>Política de retenção

As aprovações criadas do aplicativo aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento. Saiba mais sobre como [fazer backup e restaurar ambientes- \| documentos da Microsoft para plataforma de energia](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Auditoria

O aplicativo aprovações registra eventos de auditoria no centro de conformidade e segurança do Microsoft 365. Você pode exibir o log de auditoria.

1. Vá para o site de conformidade do Microsoft 365.

2. Selecione a seção **auditoria** .

3. Procure atividades em **atividades de aprovação do Microsoft Teams**.

Você pode pesquisar as seguintes atividades:

- Criar nova solicitação de aprovação

- Exibir detalhes da solicitação de aprovação

- Solicitação de aprovação aprovada

- Solicitação de aprovação rejeitada

- Solicitação de aprovação cancelada

- Solicitação de aprovação compartilhada

- Arquivo anexado à solicitação de aprovação

- Solicitação de aprovação reatribuída

- Assinatura e-assinatura para solicitação de aprovação adicionada

Para ter acesso a mais aprovações de auditoria dentro do fluxo, habilite e configure a auditoria no ambiente padrão para a aprovação de entidades de aprovação primária, solicitação de aprovação e resposta de aprovação. As operações criar, atualizar e excluir são eventos auditáveis para registros de aprovação. Saiba mais sobre [a auditoria de dados e atividades do usuário para segurança e conformidade- \| Microsoft docs para plataforma de energia](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

A auditoria pode ser personalizada ainda mais no [centro de conformidade e segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar os relatórios pré-configurados, entre em segurança e conformidade do Microsoft 365.

2. Selecione **pesquisar & investigação**.

3. Pesquisar no log de auditoria e selecionar a guia **atividades do Dynamics 365** .

Saiba mais sobre [o Microsoft dataverso e os aplicativos controlados por modelo-plataforma de energia](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Segurança

No aplicativo aprovações do Teams, os usuários têm acesso para criar novas aprovações e exibir aprovações que enviaram e receberam. Os usuários não terão acesso às aprovações criadas por outras pessoas, a menos que elas sejam um Respondente ou um visualizador da solicitação.

> [!Note]
> Um usuário receberá uma função de visualizador de uma solicitação se eles fizerem parte do chat ou do canal em que a aprovação foi criada. Elas não terão a capacidade de atuar na solicitação se não estivessem dadas essa função quando a aprovação foi criada.
