---
title: Disponibilidade do aplicativo Aprovações no Teams
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
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909515"
---
# <a name="teams-approvals-app-availability"></a>Disponibilidade dos aplicativos de aprovação do Teams

O aplicativo Aprovações está disponível como um aplicativo pessoal para todos os usuários do Microsoft Teams.
O aplicativo Aprovações oferece uma maneira simples de levar auditoria, conformidade, responsabilidade e fluxos de trabalho para Aprovações estruturadas e não estruturadas em Equipes.

 ![mostra o aplicativo aprovações](media/approvals-selection.png)

Os usuários podem fixar o aplicativo Aprovações para salvá-lo na barra de menus.

 ![mostra o aplicativo aprovações com a opção de fixar](media/approvalApp-pin.png)

A primeira aprovação criada a partir do aplicativo Aprovações acionará o provisionamento da Solução de Aprovação no ambiente padrão de CDS (Serviço de Dados Comuns). As aprovações criadas a partir do aplicativo Aprovações serão armazenadas no ambiente de CDS padrão.

Este artigo descreve os requisitos e as funções do aplicativo Aprovações.

## <a name="required-permissions-and-licenses"></a>Permissões e licenças necessárias

Para usar o aplicativo Aprovações, você precisa de permissão para os seguintes itens:

- Permissões para criar um banco de dados de CDS da Microsoft.

- Uma conta em [flow.microsoft.com](https://flow.microsoft.com/)

- Função de administrador no ambiente de destino.

- Licença para um [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), um Office 365 ou um Dynamics 365.

## <a name="storage-with-cds"></a>Armazenamento com CDS

O CDM (Modelo de Dados Comum) é a linguagem de dados compartilhada usada por aplicativos de negócios e analíticos no CDS. Ele consiste em um conjunto de esquemas de dados extensíveis padronizados publicados pela Microsoft e por nossos parceiros que permitem a consistência dos dados e seu significado em aplicativos e processos empresariais. Saiba mais sobre o [dados comuns do Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).

Saiba mais sobre o fluxo [de trabalho aprovação](https://docs.microsoft.com/power-automate/modern-approvals).

## <a name="approvals-teams-app-permissions"></a>Permissões do aplicativo Aprovações do Teams

O aplicativo Aprovações Teams permite que você acesse os seguintes recursos:

- Receba mensagens e dados que você fornece a ela.

- Enviar mensagens e notificações.

- Renderizar aplicativos pessoais e caixas de diálogo sem um header fornecido pelo Teams.

- Acesse suas informações de perfil, como nome, endereço de email, nome da empresa e idioma preferido.

- Receba mensagens e dados que os membros da equipe fornecem a ela em um canal.

- Enviar mensagens e notificações em um canal.

- Acesse as informações da sua equipe:
  - nome da equipe
  - lista de canais
  - lista de lista (nomes e endereços de email dos membros da equipe).

- Use as informações da equipe para contatá-los.

## <a name="disable-the-approvals-app"></a>Desabilitar o aplicativo Aprovações

O aplicativo Aprovações está disponível por padrão. Você pode desabilitar o aplicativo no Centro de administração do Teams.

  1. Entre no Centro de administração do Teams.

  2. Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.

  3. Procure o aplicativo Aprovações.

![mostra a navegação do Centro de administração com Aplicativos do Teams > Gerenciar Aplicativos realçada](media/manage-approval-apps.png)

  4. Selecione Aprovações.

  5. Selecione o alternância para desabilitar o aplicativo em sua organização.

![mostra os detalhes do aplicativo Aprovações](media/approvals-details.png)

## <a name="retention-policy"></a>Política de retenção

As aprovações criadas a partir do Aplicativo Aprovações são armazenadas no ambiente de CDS padrão, que não dá suporte a backups no momento. Saiba mais sobre como fazer [backup e restaurar ambientes - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).

## <a name="auditing"></a>Auditoria

O aplicativo Approvals registra eventos de auditoria no Centro de Conformidade e Segurança do Microsoft 365. Você pode exibir o log de auditoria.

1. Vá para o Site de Conformidade do Microsoft 365.

2. Selecione a **seção** Auditoria.

3. Procure atividades em atividades em **de aprovação do Microsoft Teams**.

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

Para obter acesso a mais aprovações de auditoria no Flow, habilita e configure a auditoria no ambiente padrão para as entidades de aprovação principais Aprovação, Solicitação de Aprovação e Resposta de Aprovação. Operações de criação, atualização e exclusão são eventos auditáveis para registros de Aprovação. Saiba mais sobre [dados de Auditoria e atividade do usuário para segurança e conformidade - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).

A auditoria pode ser personalizada ainda mais no [de Conformidade e Segurança do Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Para usar os relatórios pré-configurados, entre em Segurança e Conformidade do Microsoft 365.

2. Selecione **pesquisa e investigação**.

3. Pesquise no log de Auditoria e selecione **atividades do Dynamics 365** dados.

Saiba mais sobre [registro em log de atividades de aplicativos orientados por modelos e dados de aplicativos do Microsoft Dataverse - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Segurança

No aplicativo Aprovações de Equipes, os usuários têm acesso para criar novas Aprovações e exibir Aprovações que enviaram e receberam. Os usuários não terão acesso às Aprovações criadas por outras pessoas, a menos que sejam respondentes ou visualizadores da solicitação.

> [!Note]
> Um usuário terá uma função de visualizador de uma solicitação se ele for parte do chat ou canal no qual a aprovação foi criada. Ela não terá a capacidade de tomar medidas na solicitação caso não tenha sido concedida essa função quando a aprovação foi criada.
