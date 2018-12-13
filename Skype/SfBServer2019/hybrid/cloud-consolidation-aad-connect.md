---
title: Atualizar AAD conectar para incluir mais de uma floresta
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui as etapas detalhadas para a atualização AAD conectar para incluir mais de uma floresta como parte da consolidação de nuvem para equipes e Skype para negócios.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247603"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Atualizar AAD conectar para incluir mais de uma floresta

Conectar do Azure AD oferecer suporte à [sincronização de várias florestas](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). No entanto, ele oferece suporte a apenas uma instância do Azure Connect da AD está sincronizando para AAD. Portanto, em casos onde o Azure AD já estiver instalado em uma floresta, a instância existente do AAD conectar deve ser atualizada para a floresta adicional da sincronização.

 - Se todas as identidades são representadas somente uma vez entre as duas florestas (ou seja, se você ainda não tiver feito todos os contatos habilitados para email), e em seguida, você pode simplesmente execute novamente o assistente AAD conectar, escolha "Personalizar opções de sincronização" e, em seguida, no **conectar seus diretórios **página, insira o nome da floresta adicional e credenciais.<br><br>
 ![Conectar sua página de diretórios](../media/cloud-consolidation-connect-your-directories.png)
 - No entanto, se os usuários podem existir em mais de um diretório e você vai mesclando os dados (por exemplo, se existem objetos de contato em uma floresta que corresponde aos usuários em outra floresta), você precisará desinstalar Connect do Azure AD e instalá-la novamente.  Isso ocorre porque a condição de regras de ingresso entre florestas só pode ser configurada durante a instalação do primeira. Isso é feito na página a seguir:<br><br>
 ![O que identifica unicamente sua página de usuários](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>Consulte também

[Consolidação de nuvem para equipes e Skype para negócios](cloud-consolidation.md)