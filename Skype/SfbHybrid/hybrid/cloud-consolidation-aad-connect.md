---
title: Atualizar o AAD Connect para incluir mais de uma floresta
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para atualizar o AAD Connect para incluir mais de uma floresta como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160383"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Atualizar o AAD Connect para incluir mais de uma floresta

O Azure AD Connect oferece suporte à [sincronização de várias florestas](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). No entanto, ele suporta apenas uma instância da sincronização do Azure AD Connect para o AAD. Portanto, nos casos em que o Azure AD já está instalado em uma floresta, a instância existente do AAD Connect deve ser atualizada para sincronizar a partir da floresta adicional.

 - Se todas as identidades forem representadas apenas uma vez em ambas as florestas (ou seja, se você não tiver feito nenhum contato habilitado para email), poderá simplesmente executar novamente o assistente de conexão do AAD, escolher "Personalizar opções de sincronização" e, em seguida, nos **conectar seus diretórios **Insira o nome da floresta adicional e das credenciais.<br><br>
 ![A página conectar seus diretórios](../media/cloud-consolidation-connect-your-directories.png)
 - No entanto, se os usuários podem existir em mais de um diretório e você estiver mesclando os dados (por exemplo, se houver objetos de contato em uma floresta correspondente aos usuários em outra floresta), será necessário desinstalar o Azure AD Connect e reinstalá-lo.  Isso ocorre porque a condição de regras de ingresso entre florestas só pode ser configurada durante a primeira instalação. Isso é feito na seguinte página:<br><br>
 ![A página exclusivamente identificando os usuários](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)