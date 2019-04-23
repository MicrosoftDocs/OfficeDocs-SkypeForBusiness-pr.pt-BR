---
title: Aparência de linha compartilhada no Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Aparência da linha compartilhado que permite ao usuário escolher um representante para atender ou lidar com chamadas em nome deles.
ms.openlocfilehash: d16fe4b3241e814609999d8068ee47743bfca516
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993536"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aparência de linha compartilhada no Microsoft Teams

Aparência da linha compartilhado é parte do recurso de delegação que permite ao usuário escolher um representante para atender ou lidar com chamadas em nome deles. Esse recurso é útil se um usuário tiver um assistente administrativo que regularmente manipula chamadas do usuário. No contexto da aparência da linha compartilhado, um gerente é alguém que autoriza um representante para fazer ou receber chamadas em nome deles e um representante pode fazer e receber chamadas em nome de outra pessoa.

> [!IMPORTANT]
> Este recurso só está disponível no modo exclusivo para as equipes de implantação. Para obter mais detalhes sobre modos de implantação de equipes, consulte [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>É necessária uma licença

Um usuário deve ser um usuário do enterprise voice para ser um representante ou configurar a delegação e permitir que outras pessoas fazer ou receber chamadas em nome deles.

Gerentes quanto os representantes precisam ser o enterprise voice habilitado. A experiência de linha compartilhado é parte da delegação e não requer nenhuma licença adicional. Para obter detalhes adicionais sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para equipes da Microsoft](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configurando a aparência da linha compartilhada e delegação

A delegação e a aparência de linha compartilhada são recursos controlado pelo usuário: não há nenhuma configuração de administração para configurar. Para obter informações sobre como usar o recurso, consulte [compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

O administrador proprietário deve habilitar a delegação por meio da configuração de **TeamsCallingPolicy AllowDelegation** para que esse recurso funcione.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidade de recursos de aparência de linha de compartilhados

Aparência da linha compartilhada no momento é suportada pelos seguintes aplicativos e dispositivos.

| Recurso | Área de trabalho de equipes | As equipes Mac App | As equipes Web App (borda) |As equipes móveis iOS/Android App | Telefone IP de equipes |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar a delegação | Sim  | Sim  | Sim | Não | Não |
| Receber chamadas em nome de outro | Sim  | Sim  | Sim  | Sim  | Sim |
| Chamar um número de telefone em nome de outro | Sim  | Sim  | Sim  | Sim  | Sim |
| Ligue para um usuário de equipes em nome de outro | Sim  | Sim  | Sim  | Sim  | Sim |
| Consulte o modo de exibição de admin de linhas compartilhados | Sim  | Sim  | Sim | Não | Não |
| Consulte o modo de exibição de admin de atividades de chamada do gerente | Sim  | Sim  | Sim | Não | Não |
| Consulte o modo de exibição do Gerenciador de delegados | Sim  | Sim  | Sim | Não | Não |
| Admin ou Gerenciador de retenção ou retomar | Sim  | Sim  | Sim | Não | Não |

## <a name="limitations"></a>Limitações

Os gerentes podem adicionar até 25 representantes e os representantes podem ter até 25 gerentes. Não há nenhum limite no número de relações de delegação que podem ser criados em um locatário. 
 
Se o delegator e o representante não estiverem no mesmo local geográfico, é o provedor de PSTN para permitir que o ID do chamador Mostrar o de um local geográfico diferente para uma chamada delegada (em nome de). 
 
## <a name="more-information"></a>Mais informações

[Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
