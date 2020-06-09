---
title: Gerenciar grandes equipes no Microsoft Teams-práticas recomendadas
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Saiba mais sobre as práticas recomendadas para o gerenciamento de grandes equipes do Microsoft Teams para atender às necessidades da sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638901"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gerenciar grandes equipes no Microsoft Teams-práticas recomendadas
======================================================

O Microsoft Teams é igualmente eficaz para facilitar a comunicação entre pequenos grupos com dezenas de membros e grupos grandes com milhares de membros. Revisar [limites e especificações para equipes](limits-specifications-teams.md) de atualizações em tamanhos de equipe. O aumento no tamanho da equipe leva a desafios operacionais e de gerenciamento exclusivos. Este artigo descreve as práticas recomendadas para a criação e o gerenciamento de grandes equipes compostas de milhares de membros.

## <a name="value-of-large-teams"></a>Valor de equipes grandes

As grandes equipes são muito úteis para habilitar os seguintes cenários de colaboração:

- **Colaboração em todo o departamento**: se sua organização tiver vários departamentos, como finanças, operações, R&D etc., você poderá criar uma única equipe que inclua todos os membros de um departamento específico. Agora todas as comunicações relevantes para um departamento podem ser compartilhadas nesta equipe, o que facilita o acesso instantâneo e o envolvimento dos membros.

- **Colaboração em grupos de recursos de funcionários**: as organizações geralmente têm grandes grupos de pessoas com interesses mútuos que pertencem a um departamento ou grupo de trabalho diferente. Como exemplo, pode haver um grupo de pessoas que compartilham uma paixão por finanças pessoais e investimentos. Muitas vezes, é difícil conectar-se em uma grande organização. Para desenvolver comunidades para tais grupos, os administradores de locatários podem criar uma equipe grande que sirva como um grupo de recursos de toda a empresa pública que qualquer pessoa pode participar e aproveitar. Por fim, essas comunidades coletam informações que podem ser aproveitadas por membros novos e existentes.

- **Colaboração entre membros internos e externos**: produtos populares muitas vezes desenvolvem uma comunidade de pioneiros que estão ansiosos para experimentar novas versões de produtos e enviar comentários. Pioneiros desenvolve uma relação com grupos de produtos para ajudar a moldar o produto. Nesses cenários, os administradores de locatários podem configurar uma equipe grande que inclui grupos de produtos internos e avaliadores de produtos externos para facilitar um processo avançado de desenvolvimento de produtos. Essas equipes também podem fornecer suporte ao cliente para um conjunto de clientes selecionado.

## <a name="create-teams-from-existing-groups"></a>Criar equipes a partir de grupos existentes

Use grupos de contatos, grupos de segurança ou grupos do Office para começar a equipe. Você pode importar um grupo para criar uma equipe ou criar uma equipe a partir de um grupo do Office.

**Importar um grupo para criar uma equipe**: quando você importa um grupo com até 3.500 membros para o Teams, o Microsoft Teams calcula automaticamente o número total de membros do grupo. Esta é uma importação única e alterações futuras no grupo não serão atualizadas automaticamente no Teams.

**Criar uma equipe a partir de um grande grupo do microsoft 365**: quando você cria uma equipe a partir de um grande grupo do Microsoft 365, os membros fazem parte automaticamente do grupo Microsoft 365 **e** da equipe. No futuro, como os membros da equipe se unem ou deixam o grupo do Microsoft 365, eles são automaticamente adicionados ou removidos da equipe.

## <a name="create-channels-to-focus-discussions"></a>Crie canais para concentrar discussões

Você pode restringir as discussões em grupo criando canais enfocados. Confira [práticas recomendadas para organizar equipes](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Restringir a criação de canais

Se algum membro da equipe tiver permissão para criar canais, essa equipe poderá ter acúmulo de canais. Os proprietários de equipe devem desativar a criação, a atualização, a exclusão e a restauração dos membros em **configurações > permissões de membros**. Consulte [visão geral de equipes e canais](teams-channels-overview.md).

![Imagem da tela que mostra a seção permissões de membro da guia Configurações do console de administração.](media/no-channel-creation.png "Imagem da tela que é a seção permissões de membro da guia Configurações do console de administração. A opção permitir que membros criem ou excluir canais está desmarcada.")

## <a name="add-favorite-channels"></a>Adicionar canais favoritos

Para acelerar o novo envolvimento do usuário e a descoberta de conteúdo, você pode selecionar os canais favoritos que estão disponíveis para o usuário por padrão. No painel **canais** do centro de administração, marque os canais na coluna **mostrar para membros** .

![Imagem da tela que mostra o painel canais do console de administração.](media/favorite-channels.png "Imagem da tela que mostra o painel canais do console de administração. Alguns canais são verificados para exibição para membros.")

 Consulte [criar suas primeiras equipes e canais](get-started-with-teams-create-your-first-teams-and-channels.md) para obter detalhes.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regulari aplicativos e bots em equipes grandes

Para impedir a inclusão de aplicativos ou bots indesejados, os proprietários da equipe podem desabilitar, adicionar, remover e carregar aplicativos e conectores para os membros da equipe. No centro de administração, em **configurações > permissões de membro**, desmarque as três opções que permitem aos membros adicionar aplicativos ou conectores.

![Imagem da tela que mostra a seção permissões de membro do painel configurações.](media/disable-bots-connectors.png "Imagem da tela que mostra a seção permissão de membro do painel configurações. As opções para permitir que os membros adicionem aplicativos ou conectores estão desmarcadas.")

Consulte [aplicativos, bots & conectores](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regular menção de equipe e de canal

As menção de equipe e de canal podem ser usadas para chamar a atenção de toda a equipe para determinadas Postagens de canal. Quando uma menção é usada em uma postagem, uma notificação é enviada para milhares de membros da equipe. Se as notificações forem muito frequentes, os membros da equipe poderão ficar sobrecarregados e poderão reclamar com os proprietários da equipe. Para impedir que a equipe ou o canal mencionem, desative as caixas no painel configurações do Teams e de canal para os membros desmarcando as caixas no painel configurações do teams **> @mentions** .

![Imagem da tela que mostra a seção em menção do painel configurações.](media/no-at-mentions.png "Imagem da tela que mostra a seção em menção do painel configurações. As opções para mostrar e conceder acesso a membros em menção são desmarcadas.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considerar a configuração da moderação em seus canais

Os proprietários da equipe podem ativar a moderação de um canal para controlar quem pode iniciar novas postagens e responder a postagens no canal. Ao configurar a moderação, você pode escolher um ou mais membros da equipe para serem moderadores. Os proprietários da equipe são Moderadores por padrão. Para obter mais informações, consulte [configurar e gerenciar a moderação do canal](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Práticas recomendadas para organizar equipes](best-practices-organizing.md)
- [Criar uma equipe de toda a organização](create-an-org-wide-team.md)
