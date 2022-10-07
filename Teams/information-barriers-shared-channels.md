---
title: Barreiras de informações e canais compartilhados (versão prévia)
description: Este artigo explica como as barreiras de informações no Microsoft Teams dão suporte a Canais Compartilhados
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: 5b214a4c60df7b50f508fec7985c6f38b65985e6
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047211"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Barreiras de informações e canais compartilhados (versão prévia)

[Os canais compartilhados](shared-channels.md) no Microsoft Teams criam espaços de colaboração em que você pode convidar pessoas que não estão na equipe. [As Barreiras de Informações do Microsoft Purview](/microsoft-365/compliance/information-barriers) são políticas que podem ser implementadas para restringir e impedir que usuários e grupos se comuniquem entre si dentro e fora de sua organização.

Os canais compartilhados são habilitados por padrão no Teams. Você pode escolher se as pessoas podem criar canais compartilhados, se elas podem compartilhá-los com pessoas de fora da sua organização e se elas podem participar de canais compartilhados externos criando uma política de canal. Quando as políticas de barreiras de informações são configuradas em sua organização, as verificações são executadas ao configurar canais compartilhados para verificar se nenhum dos membros do canal existente e os novos usuários adicionados ao canal compartilhado violam as condições da política de barreiras de informações.

Use a tabela a seguir para entender como as políticas de barreiras de informações podem afetar as comunicações e resultar em comportamentos específicos ao configurar canais compartilhados:

|**Cenário**|**Comportamento de barreiras de informações**|
|:-----------|:--------------------------------|
| **Compartilhar um canal com um usuário em sua organização** | Se o usuário não tiver permissão para se comunicar com membros de canal compartilhado por uma política de barreiras de informações, o usuário não será exibido na pesquisa de usuário e o canal não será compartilhado com a equipe. <br><br> Se o usuário não puder ser adicionado de acordo com uma política de barreiras de informações, você verá a seguinte mensagem: Não encontramos *nenhuma correspondente. Fale com o administrador de TI sobre como expandir o escopo da pesquisa.* |
| **Compartilhar um canal em sua organização com outra equipe que você possui** | Se a outra equipe tiver usuários que não têm permissão para se comunicar com membros de canal compartilhado por uma política de barreiras de informações, o canal não será compartilhado com a equipe. <br><br> Se as comunicações não forem permitidas por uma política de barreiras de informações, você verá a seguinte mensagem: O canal não pode *ser compartilhado com essa equipe. Escolha outra equipe ou entre em contato com o administrador para obter mais informações.* |
| **Compartilhar um canal em sua organização com outra equipe que você não possui** | Se o proprietário da equipe ou qualquer usuário da outra equipe não tiver permissão para se comunicar com membros de canal compartilhado por uma política de barreiras de informações, o canal não poderá ser compartilhado com a equipe. <br><br> Se as comunicações não forem permitidas por uma política de barreiras de informações, você verá a seguinte mensagem: O canal não pode *ser compartilhado com essa equipe. Escolha outra equipe ou entre em contato com o administrador para obter mais informações.* |
| **Adicionar um novo usuário à equipe quando a equipe tiver compartilhado canais com outras equipes** | Se o novo usuário não tiver permissão para se comunicar com membros da equipe de canal compartilhado por uma política de barreiras de informações, o usuário não poderá ser adicionado à equipe. Quando você está adicionando um usuário a uma equipe com seis ou mais canais compartilhados, o usuário é adicionado imediatamente ao canal e há suporte para compartilhamento. O compartilhamento da equipe e dos canais compartilhados anteriormente poderá ser interrompido se o novo usuário for considerado não compatível com uma política de barreiras de informações.<br><br> Se o usuário não puder ser adicionado por uma política de barreiras de informações, você verá a seguinte mensagem: Não é possível adicionar o usuário devido a uma política de *barreiras de informações.* |
| **Compartilhar um canal com uma equipe externa** | As políticas de barreiras de informações em locatários internos e externos não restringem as comunicações entre usuários de locatários diferentes. Canais compartilhados estão disponíveis para serem compartilhados com usuários externos. |
