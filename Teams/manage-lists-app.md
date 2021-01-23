---
title: Gerenciar o aplicativo listas para a sua organização
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Saiba como gerenciar o aplicativo listas no Teams para usuários em sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365initiative-lists
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: e0fb125ede9300395e045a0c5640abd075547562
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944606"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Gerenciar o aplicativo listas para sua organização no Microsoft Teams

## <a name="overview-of-lists"></a>Visão geral de listas

O aplicativo listas no Microsoft Teams ajuda os usuários em sua organização a acompanhar informações, organizar o trabalho e gerenciar fluxos de trabalho. Com listas, os usuários podem controlar dados como problemas, ativos, rotinas, contatos, inventário, incidentes, empréstimos, pacientes e muito mais usando modos de exibição, regras e alertas personalizáveis para manter todos os membros da equipe em sincronia.

No Teams, os usuários acessam listas como uma guia em um canal. Clique **+** para abrir a Galeria de guias e adicionar uma nova instância da guia do aplicativo de listas a um canal para começar.

![Aplicativo listas na Galeria de guias](media/lists-tab.png)

Os usuários podem criar novas listas ou fixar listas existentes dentro da mesma equipe ou de outro site do SharePoint ao qual tenham acesso. Novas listas podem ser criadas do zero, de modelos internos, com base na estrutura de uma lista existente ou pela importação de dados de uma pasta de trabalho do Excel. O aplicativo listas está disponível em Teams desktop, Web e clientes móveis.

![como criar uma lista no aplicativo listas](media/lists-create-list.png)

## <a name="templates"></a>Modelos

Os modelos em listas são adaptados para cenários comuns de controle de informações para usuários. Cada modelo vem com uma estrutura de lista predefinida, layouts de formulário e opções de formatação no modo de exibição de lista e em um nível de exibição de detalhes para ajudar os usuários a começar a usar rapidamente. Depois de selecionar um modelo, os usuários obtêm uma visualização de como será a aparência da lista, juntamente com alguns dados de exemplo. Veja a seguir alguns exemplos de como as equipes em sua organização podem usar os modelos predefinidos nas listas:

- Controlar problemas e trazê-los para fechar usando o modelo de controlador de problemas.
- Organize todos os detalhes do evento com o modelo de itinerário do evento.
- Use o modelo pacientes para registrar as necessidades e o status de pacientes para equipes de saúde em sua organização de assistência médica para monitorar e coordenar o cuidado.
- Acompanhar o status dos aplicativos de empréstimo com o modelo empréstimos.

## <a name="example-scenario"></a>Cenário de exemplo

Uma agência postal local é responsável pela classificação e entrega de emails em seu bairro. A cada manhã, a agência postal tem um huddle de equipe para analisar metas diárias, compartilhar comunicados e discutir incidentes conhecidos.

Após a huddle, as transportadoras de email captam seus emails e iniciam a rota de entrega. Os incidentes podem ocorrer ao longo de uma rota, por exemplo, um problema de veículo, um problema relacionado com o cachorro ou um protesto de desrepouso social. Quando as transportadoras de email encontram um incidente, elas usam o Microsoft Teams em seus dispositivos móveis para registrar os detalhes do incidente, que são rastreados em uma lista no canal de equipe. Todas as pessoas da equipe, incluindo operadoras de email no campo, podem ver essas informações e se manterem informadas.

Antes de mudar para o Teams, as operadoras de email precisavam voltar para a postagem completa de um formulário de cópia impressa para denunciar um incidente inserido em uma planilha do Excel. O Teams oferece às operadoras de e-mail um celular em primeiro lugar, experiência onde eles podem usar listas para denunciar incidentes no campo conforme eles acontecem, compartilhar detalhes do incidente com os membros da equipe, conversar sobre eles no canal e conduzir incidentes para resolução.

## <a name="what-you-need-to-know-about-lists"></a>O que você precisa saber sobre listas

### <a name="lists-is-available-in-every-team-and-channel"></a>Listas está disponível em todas as equipes e canais

As listas são pré-instaladas para todos os usuários do Teams e estão disponíveis diretamente na Galeria de guias de todas as equipes e canais. Isso significa que os usuários não precisam acessar a App Store Teams para instalá-lo.

### <a name="lists-and-sharepoint"></a>Listas e SharePoint

Lista os dados são armazenados no site de equipe do SharePoint Online. Para saber mais sobre como o SharePoint Online interage com o Microsoft Teams, consulte [como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](SharePoint-OneDrive-interact.md).

As permissões definidas no SharePoint aplicam-se às listas criadas no aplicativo listas. Por padrão, as listas herdam permissões do site ao qual elas pertencem. Essas permissões controlam os tipos de ações que os usuários podem fazer, como se podem criar ou editar listas. Para saber mais, consulte [níveis de permissão no SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) e [permissões de usuário e níveis de permissão no SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).

Em determinados cenários, talvez você queira restringir quais ações os usuários podem fazer em listas. Por exemplo, uma pessoa em uma equipe edita um modo de exibição de lista, que o altera para todos os membros da equipe e você deseja permitir que somente o proprietário da equipe ou certos membros da equipe editem modos de exibição de lista. Para saber mais, confira [Personalizar permissões para uma lista ou biblioteca do SharePoint](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> Neste ponto, as permissões de proprietário e membro de uma equipe não estão vinculadas de maneira alguma às permissões no site de equipe que governam o comportamento de listas ou do aplicativo listas. No entanto, com base nos comentários e no uso do cliente, isso será considerado para uma iteração futura do produto.  

### <a name="limitations"></a>Relacionadas

Com listas, os usuários obtêm uma experiência na área de trabalho, Web e celular. É importante saber que os usuários não podem criar novas listas ou fixar listas existentes usando listas no cliente móvel do teams. Para exibir ou editar uma lista no cliente móvel do Teams, uma lista deve ser criada primeiro ou adicionada usando listas na área de trabalho do teams ou no cliente da Web.

Convidados não podem criar ou excluir uma lista. Elas podem adicionar itens de lista a listas existentes, iniciar novas conversas sobre itens de lista e responder a conversas existentes sobre itens de lista.

### <a name="lists-and-the-sharepoint-app"></a>Listas e o aplicativo do SharePoint

Se os usuários em sua organização criaram listas usando o aplicativo do SharePoint, essas listas serão automaticamente movidas para listas sem qualquer ação necessária do usuário. Para obter a melhor e mais rica experiência de integração de listas no Microsoft Teams, use o aplicativo listas e fixe suas listas existentes.

## <a name="set-up-lists"></a>Configurar listas

### <a name="enable-or-disable-lists-in-your-organization"></a>Habilitar ou desabilitar listas em sua organização

Listas é habilitado por padrão para todos os usuários do teams em sua organização. Você pode desativar ou ativar o aplicativo no nível da organização na página [gerenciar aplicativos](manage-apps.md) no centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos** .
2. Siga um destes procedimentos:

    - Para desativar listas para a sua organização, procure o aplicativo listas, selecione-o e clique em **Bloquear**.
    - Para ativar listas para a sua organização, procure o aplicativo listas, selecione-o e clique em **permitir**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Habilitar ou desabilitar listas para usuários específicos em sua organização

Para permitir ou bloquear usuários específicos em sua organização usando listas, verifique se a opção listas está ativada para sua organização na página [gerenciar aplicativos](manage-apps.md) e crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários. Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Pesquisar eventos de lista no log de auditoria

As listas são habilitadas com auditoria de nível empresarial para que você possa Pesquisar listas e eventos de item de lista no log de auditoria no centro de conformidade do & de segurança. Para saber mais, confira [Pesquisar no log de auditoria no centro de conformidade do & de segurança](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Para obter uma lista de eventos de auditoria que são relevantes para o aplicativo listas no Teams, consulte [atividades da lista do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Para que você possa Pesquisar no log de auditoria, primeiro ative a auditoria no [centro de conformidade do & de segurança](https://protection.office.com). Lembre-se de que os dados de auditoria estão disponíveis apenas no ponto em que você ativou a auditoria.

## <a name="power-automate-power-apps-and-graph-api"></a>Automação de energia, aplicativos de energia e API de gráfico

As listas dão suporte à [automatização de energia](https://docs.microsoft.com/power-automate/flow-types) para fluxos de trabalho e [aplicativos de energia](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) para formulários de lista. Os desenvolvedores podem usar a [API Lists](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) para conectar os dados da lista como uma fonte por meio do Microsoft Graph.

## <a name="give-feedback-or-report-an-issue"></a>Enviar comentários ou relatar um problema
  
Para nos enviar comentários ou reportar um problema, clique em **ajuda** próximo à parte inferior do painel de navegação esquerdo no Teams e selecione **relatar um problema**. Selecione **listas** e, em seguida, insira seus comentários ou detalhes sobre o problema que está ocorrendo.

## <a name="related-topics"></a>Tópicos relacionados

- [Lista ajuda documentação](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
