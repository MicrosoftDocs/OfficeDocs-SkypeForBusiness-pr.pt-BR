---
title: Gerenciar equipes grandes em Microsoft Teams práticas recomendadas
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Saiba mais sobre as práticas recomendadas para gerenciar equipes grandes Microsoft Teams para atender às necessidades da sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fff84bd660eb19f01c6a7e3388f5289b09896401
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856340"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gerenciar equipes grandes em Microsoft Teams - Práticas recomendadas

Microsoft Teams é igualmente eficaz para facilitar as comunicações entre pequenos grupos com dezenas de membros e grupos grandes com milhares de membros. Revise [limites e especificações para Teams](limits-specifications-teams.md) para atualizações em tamanhos de equipe. O aumento do tamanho da equipe leva a desafios operacionais e de gerenciamento exclusivos. Este artigo descreve as práticas recomendadas para criar e gerenciar equipes grandes compostas por milhares de membros.

## <a name="value-of-large-teams"></a>Valor de equipes grandes

As equipes grandes são muito úteis na habilitação dos seguintes cenários de colaboração:

- Colaboração em todo o departamento **:** se sua organização tiver vários departamentos, como Finanças, Operações, R&D etc., você poderá criar uma única equipe que inclua todos os membros em um departamento específico. Agora, todas as comunicações relevantes para um departamento podem ser compartilhadas nesta equipe, o que facilita o acesso instantâneo e o envolvimento dos membros.

- **Colaboração em grupos de recursos de** funcionários : as organizações geralmente têm grandes grupos de pessoas com interesses mútuos que pertencem a um departamento ou grupo de trabalho diferente. Por exemplo, pode haver um grupo de pessoas que compartilham uma paixão por finanças pessoais e investimentos. Geralmente, é difícil se conectar em uma organização grande. Para desenvolver comunidades para esses grupos, os administradores de locatários podem criar uma grande equipe que serve como um grupo de recursos público em toda a empresa que qualquer pessoa pode ingressar e aproveitar. Eventualmente, essas comunidades coletam informações que membros novos e existentes podem aproveitar.

- **Colaboração entre membros internos e** externos : os produtos populares geralmente desenvolvem uma comunidade de usuários in-loco que estão ansiosos para experimentar novas versões de produtos e fornecer comentários. Os primeiros adotantes desenvolvem uma relação com grupos de produtos para ajudar a moldar o produto. Nesses cenários, os administradores de locatários podem configurar uma grande equipe que inclui grupos de produtos internos e avaliadores de produtos externos para facilitar um processo de desenvolvimento de produtos ricos. Essas equipes também podem fornecer suporte ao cliente para um conjunto selecionado de clientes.

## <a name="create-teams-from-existing-groups"></a>Criar equipes de grupos existentes

Use grupos de contatos, grupos de segurança ou grupos Office para iniciar sua equipe. Você pode importar um grupo para criar uma equipe ou criar uma equipe de Office grupo.

**Importar um** grupo para fazer uma equipe : quando você importa um grupo com até 3.500 membros para Teams, o Teams calcula automaticamente o número total de membros no grupo. Essa é uma importação única e as alterações futuras no grupo não serão atualizadas automaticamente no Teams.

**Criar uma equipe de** um grupo de Microsoft 365 grande : quando você cria uma equipe de um grupo de Microsoft 365 grande, os membros fazem automaticamente parte do grupo Microsoft 365 **e** da equipe. No futuro, à medida que os membros da equipe ingressam ou saem do grupo de Microsoft 365, eles são adicionados ou removidos automaticamente da equipe.

## <a name="bulk-importexportremove-members-in-a-team"></a>Importar/exportar/remover membros em massa em uma equipe

O portal do Azure permite que os usuários importem/exportem/removam membros em massa em um Microsoft 365 Group. Para obter mais informações, consulte [To bulk import group members](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members).

Como todas as equipes são apoiadas por um grupo de Microsoft 365, você pode usar o portal do Azure para executar essas operações no grupo correspondente à equipe. As operações de membro serão refletidas na equipe dentro de 24 horas.

## <a name="create-channels-to-focus-discussions"></a>Crie canais para concentrar discussões

Você pode restringir as discussões de grupo criando canais focados. Consulte [Práticas recomendadas para organizar equipes.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>Restringir a criação de canal

Se qualquer membro da equipe tiver permissão para criar canais, essa equipe poderá ter expansão de canal. Os proprietários de equipe devem desativar a criação, a atualização, a exclusão e a restauração do canal para os membros **Configurações > permissões de membro.** Consulte [Visão geral das equipes e canais.](teams-channels-overview.md)

![Imagem de tela que mostra a seção permissões de membro da guia console de Configurações administrador.](media/no-channel-creation.png "Imagem de tela que a seção permissões de membro da guia console de Configurações administrador. As opções de permitir que os membros criem ou excluam canais são desmarcadas.")

## <a name="add-favorite-channels"></a>Adicionar canais favoritos

Para acelerar o novo envolvimento do usuário e a descoberta de conteúdo, você pode selecionar canais favoritos disponíveis para o usuário por padrão. No painel **Canais** do centro de administração, verifique os canais na **coluna Mostrar para membros.**

![Imagem de tela que mostra o painel de canais do console de administração.](media/favorite-channels.png "Imagem de tela que mostra o painel de canais do console de administração. Alguns canais são verificados para Mostrar membros.")

 Confira [Criar suas primeiras equipes e canais para](get-started-with-teams-create-your-first-teams-and-channels.md) obter detalhes.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regular aplicativos e bots em equipes grandes

Para evitar a adição de aplicativos ou bots de distrações, os proprietários de equipe podem desabilitar, adicionar, remover e carregar aplicativos e conectores para membros da equipe. No centro de administração sob Configurações > Permissões de membro, **desmarque** as três opções que permitem que os membros adicionem aplicativos ou conectores.

![Imagem de tela que mostra a seção Permissões de membro do painel de Configurações.](media/disable-bots-connectors.png "Imagem de tela que mostra a seção Permissão Membro do Configurações painel. As opções para permitir que os membros adicionem aplicativos ou conectores são desmarcadas.")

Consulte [Aplicativos, bots, & conectores](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regular as menções de equipe e canal

As menções de equipe e canal podem ser usadas para chamar a atenção de toda a equipe para determinadas postagens de canal. Depois que uma menção é usada em uma postagem, uma notificação é enviada a milhares de membros da equipe. Se as notificações são muito frequentes, os membros da equipe podem ficar sobrecarregados e podem se queixar aos proprietários da equipe. Para evitar menções de equipe ou canal, desligue as menções de equipe e canal para membros desmarcando as caixas no painel **de** equipes Configurações > @mentions painel.

![Imagem de tela que mostra a seção em Menções do painel de Configurações.](media/no-at-mentions.png "Imagem de tela que mostra a seção em Menções do painel de Configurações. As opções para mostrar e dar aos membros acesso às menções são desmarcadas.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considerar a configuração da moderação em seus canais

Os proprietários da equipe podem ativar a moderação de um canal para controlar quem pode iniciar novas postagens e responder a postagens no canal. Ao configurar a moderação, você pode escolher um ou mais membros da equipe para serem moderadores. Os proprietários da equipe são moderadores por padrão. Para obter mais informações, [consulte Configurar e gerenciar a moderação do canal](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Práticas recomendadas para organizar Teams](best-practices-organizing.md)
- [Criar uma equipe em toda a organização](create-an-org-wide-team.md)