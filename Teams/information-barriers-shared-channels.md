---
title: Barreiras de informações e canais compartilhados (visualização)
description: Este artigo explica como as barreiras de informações no Microsoft Teams suportam Canais Compartilhados
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712112"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Barreiras de informações e canais compartilhados (visualização)

[Canais compartilhados](shared-channels.md) Microsoft Teams criar espaços de colaboração onde você pode convidar pessoas que não estão na equipe. [Barreiras de informações](/microsoft-365/compliance/information-barriers) são políticas que podem ser implementadas para restringir e impedir que usuários e grupos se comuniquem uns com os outros dentro e fora de sua organização.

Os canais compartilhados são habilitados por padrão Teams. Você pode escolher se as pessoas podem criar canais compartilhados, se elas podem compartilhá-los com pessoas de fora da sua organização e se elas podem participar de canais compartilhados externos criando uma política de canal. Quando as políticas de barreiras de informações são configuradas em sua organização, as verificações são executadas ao configurar canais compartilhados para verificar se nenhum membro do canal existente e os novos usuários adicionados ao canal compartilhado violam as condições da política de barreiras de informações.

Use a tabela a seguir para entender como as políticas de barreiras de informações podem afetar as comunicações e resultar em comportamentos específicos ao configurar canais compartilhados:

|**Cenário**|**Comportamento de barreiras de informações**|
|:-----------|:--------------------------------|
| **Compartilhar um canal com um usuário em sua organização** | Se o usuário não tiver permissão para se comunicar com membros de canal compartilhado por uma política de barreiras de informações, o usuário não será exibido na pesquisa do usuário e o canal não será compartilhado com a equipe. <br><br> Se o usuário não puder ser adicionado por uma política de barreiras de informações, você verá a seguinte mensagem: *Não encontramos nenhuma corresponde. Fale com o administrador de IT sobre como expandir o escopo da sua pesquisa.* |
| **Compartilhar um canal em sua organização com outra equipe que você possui** | Se a outra equipe tiver qualquer usuário que não tenha permissão para se comunicar com membros de canal compartilhado por uma política de barreiras de informações, o canal não será compartilhado com a equipe. <br><br> Se as comunicações não são permitidas por uma política de barreiras de informações, você verá a seguinte mensagem: O canal não pode *ser compartilhado com essa equipe. Escolha outra equipe ou entre em contato com o administrador para obter mais informações.* |
| **Compartilhar um canal em sua organização com outra equipe que você não possui** | Se o proprietário da equipe ou qualquer usuário da outra equipe não tiver permissão para se comunicar com membros de canal compartilhado por uma política de barreiras de informações, o canal não poderá ser compartilhado com a equipe. <br><br> Se as comunicações não são permitidas por uma política de barreiras de informações, você verá a seguinte mensagem: O canal não pode *ser compartilhado com essa equipe. Escolha outra equipe ou entre em contato com o administrador para obter mais informações.* |
| **Adicionar um novo usuário à equipe quando a equipe tiver compartilhado canais com outras equipes** | Se o novo usuário não tiver permissão para se comunicar com membros da equipe de canal compartilhado por uma política de barreiras de informações, o usuário não poderá ser adicionado à equipe. Quando você adiciona um usuário a uma equipe com seis ou mais canais compartilhados, o usuário é adicionado imediatamente ao canal e há suporte para compartilhamento. O compartilhamento para a equipe e os canais compartilhados anteriormente pode ser interrompido se o novo usuário for considerado não compatível com uma política de barreiras de informações.<br><br> Se o usuário não puder ser adicionado por uma política de barreiras de informações, você verá a seguinte mensagem: Não é possível adicionar o usuário devido a uma política de *barreiras de informações.* |
| **Compartilhar um canal com uma equipe externa** | As políticas de barreiras de informações em locatários internos e externos não restringem as comunicações entre os usuários dos diferentes locatários. Canais compartilhados estão disponíveis para serem compartilhados com usuários externos. |
