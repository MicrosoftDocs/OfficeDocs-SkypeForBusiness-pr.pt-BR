---
title: Gerenciar equipes grandes no Microsoft Teams - melhores práticas
ms.reviewer: abgupta
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Saiba mais sobre as melhores práticas para gerenciar grandes equipes no Microsoft Teams para atender às necessidades da sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: fddf4b5cf80c51977b2a57ceceac8a07e529c51f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199073"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gerenciar equipes grandes no Microsoft Teams – Melhores práticas

Microsoft Teams é igualmente eficaz em facilitar as comunicações entre pequenos grupos com dezenas de membros e grandes grupos com milhares de membros. Examine [limites e especificações do Teams para](limits-specifications-teams.md) obter atualizações sobre tamanhos de equipe. O aumento do tamanho da equipe leva a desafios operacionais e de gerenciamento exclusivos. Este artigo descreve as melhores práticas para criar e gerenciar grandes equipes compostas por milhares de membros.

## <a name="value-of-large-teams"></a>Valor de equipes grandes

Equipes grandes são muito úteis para habilitar os seguintes cenários de colaboração:

- **Colaboração em todo o departamento**: se sua organização tiver vários departamentos, como Finanças, Operações, R&D etc., você poderá criar uma única equipe que inclua todos os membros em um departamento específico. Agora, todas as comunicações relevantes para um departamento podem ser compartilhadas nesta equipe, o que facilita o alcance instantâneo e o engajamento dos membros.

- **Colaboração em grupos de recursos de funcionários**: as organizações geralmente têm grandes grupos de pessoas com interesses mútuos que pertencem a um departamento ou grupo de trabalho diferente. Como exemplo, pode haver um grupo de pessoas que compartilham uma paixão por finanças pessoais e investimentos. Muitas vezes é difícil se conectar em uma organização grande. Para desenvolver comunidades para esses grupos, os administradores de locatários podem criar uma grande equipe que serve como um grupo de recursos público em toda a empresa que qualquer pessoa pode ingressar e aproveitar. Eventualmente, essas comunidades coletam informações que os membros novos e existentes podem desfrutar.

- **Colaboração entre membros internos e externos**: os produtos populares geralmente desenvolvem uma comunidade de adotantes iniciais que estão ansiosos para experimentar novas versões de produtos e fornecer comentários. Os primeiros adotantes desenvolvem uma relação com grupos de produtos para ajudar a moldar o produto. Nesses cenários, os administradores de locatários podem configurar uma grande equipe que inclui grupos de produtos internos e avaliadores de produtos externos para facilitar um processo avançado de desenvolvimento de produtos. Essas equipes também podem fornecer suporte ao cliente para um conjunto seleto de clientes.

## <a name="create-teams-from-existing-groups"></a>Criar equipes de grupos existentes

Use grupos de contatos, grupos de segurança ou grupos do Office para iniciar sua equipe. Você pode importar um grupo para criar uma equipe ou criar uma equipe de um grupo do Office.

**Importar um grupo para criar uma equipe**: quando você importa um grupo com até 3.500 membros para o Teams, o Teams calcula automaticamente o número total de membros no grupo. Essa é uma importação única e as alterações futuras no grupo não serão atualizadas automaticamente no Teams.

**Crie uma equipe de um grande grupo Microsoft 365**: quando você cria uma equipe de um grande grupo Microsoft 365, os membros fazem parte automaticamente do grupo Microsoft 365 **e** da equipe. No futuro, à medida que os membros da equipe ingressarem ou deixarem o grupo Microsoft 365, eles serão adicionados ou removidos automaticamente da equipe.

## <a name="bulk-importexportremove-members-in-a-team"></a>Importar/exportar/remover membros em massa em uma equipe

O portal do Azure permite que os usuários importem/exportem/removam membros em massa em um grupo Microsoft 365. Para obter mais informações, consulte [Para importar em massa membros do grupo](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members).

Como cada equipe é apoiada por um grupo Microsoft 365, você pode usar o portal do Azure para executar essas operações no grupo correspondente à equipe. As operações de membro serão refletidas na equipe dentro de 24 horas.

## <a name="create-channels-to-focus-discussions"></a>Crie canais para concentrar discussões

Você pode restringir as discussões em grupo criando canais focados. Confira [Melhores práticas para organizar equipes](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Restringir a criação de canal

Se algum membro da equipe tiver permissão para criar canais, essa equipe poderá ter expansão de canal. Os proprietários da equipe devem desativar a criação, atualização, exclusão e restauração de **canais para membros em Configurações > permissões de membro**. Confira [Visão geral de equipes e canais](teams-channels-overview.md).

![Imagem de tela que mostra a seção permissões de membro da guia Configurações do console de administração.](media/no-channel-creation.png "Imagem de tela que o membro permissões seção da guia Configurações do console de administrador. As opções permitir que os membros criem ou excluam canais são desmarcadas.")

## <a name="add-favorite-channels"></a>Adicionar canais favoritos

Para acelerar o novo envolvimento do usuário e a descoberta de conteúdo, você pode selecionar canais favoritos que estão disponíveis para o usuário por padrão. No painel **Canais** do centro de administração, verifique os canais na coluna **Mostrar para membros** .

![Imagem de tela que mostra o painel de canais do console de administração.](media/favorite-channels.png "Imagem de tela que mostra o painel de canais do console de administração. Alguns canais são verificados para Mostrar para membros.")

 Consulte [Criar suas primeiras equipes e canais](get-started-with-teams-create-your-first-teams-and-channels.md) para obter detalhes.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regular aplicativos e bots em grandes equipes

Para evitar a adição de aplicativos ou bots de distração, os proprietários da equipe podem desabilitar, adicionar, remover e carregar aplicativos e conectores para membros da equipe. No centro de administração em **Configurações > permissões de membro, desmarque** as três opções que permitem que os membros adicionem aplicativos ou conectores.

![Imagem de tela que mostra a seção Permissões de membro do painel Configurações.](media/disable-bots-connectors.png "Imagem de tela que mostra a seção Permissão do membro do painel Configurações. As opções para permitir que os membros adicionem aplicativos ou conectores são desmarcadas.")

Confira [visão geral dos aplicativos do Teams](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regular menções de equipe e canal

As menções de equipe e canal podem ser usadas para chamar a atenção de toda a equipe para determinadas postagens de canal. Depois que uma menção é usada em uma postagem, uma notificação é enviada a milhares de membros da equipe. Se as notificações forem muito frequentes, os membros da equipe poderão ficar sobrecarregados e reclamar com os proprietários da equipe. Para evitar menções de equipe ou canal, desative as menções de equipe e canal para membros **desmarcando as caixas no painel Configurações do teams > @mentions** .

![Imagem de tela que mostra a seção em Menções do painel Configurações.](media/no-at-mentions.png "Imagem de tela que mostra a seção em Menções do painel Configurações. As opções para mostrar e dar acesso aos membros em menções são desmarcadas.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considerar a configuração da moderação em seus canais

Os proprietários da equipe podem ativar a moderação de um canal para controlar quem pode iniciar novas postagens e responder a postagens no canal. Ao configurar a moderação, você pode escolher um ou mais membros da equipe para serem moderadores. Os proprietários da equipe são moderadores por padrão. Para obter mais informações, consulte [Configurar e gerenciar a moderação do canal](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Melhores práticas para organizar o Teams](best-practices-organizing.md)
- [Criar uma equipe em toda a organização](create-an-org-wide-team.md)