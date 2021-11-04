---
title: Definir o escopo da implantação do E9-1-1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisões necessárias para o planejamento de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: b576f2d9e7dbf9cb82484803ca6e93afb4440795
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777991"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definir o escopo da implantação do E9-1-1 no Skype for Business Server

Decisões necessárias para o planejamento de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.

Antes de configurar Skype for Business para o E9-1-1, você precisa planejar sua implantação do E9-1-1. Algumas das questões a serem consideradas são:

 **Quais são as obrigações legais e políticas da sua organização em relação ao E9-1-1?**

 Os requisitos legais de E9-1-1 para PBXs (chamados de Multi-line Telephone Systems, ou MLTS, no linguajar de E9-1-1) diferem de acordo com o estado. Você deve consultar sua equipe jurídica para entender as obrigações que podem se aplicar à sua implantação de Skype for Business em suas geografias relevantes.

 **Quais áreas dentro de sua empresa precisam estar habilitadas para E9-1-1?**

 É possível habilitar o E9-1-1 para toda a empresa ou para locais selecionados. Por exemplo, talvez você tenha requisitos variados de E9-1-1 para escritórios em estados diferentes ou queira excluir sites fora dos EUA.

 **Como você implantará o E9-1-1 em sites de filiais?**

 A resiliência de voz é um conceito importante para compreender quando implantar o E9-1-1 no site local. Se você tiver centralizado troncos SIP do E-9-1-1 e ocorrer uma paralisação de WAN, os clientes que entrarem podem não conseguir obter um local do serviço de Informações de Local ou se conectar ao provedor de serviços de emergência. Skype for Business fornece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: ter redes de dados resilientes, implantar um tronco SIP em cada filial ou enviar chamadas de emergência para o gateway local durante paralisações. Para obter detalhes, consulte [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).

 **Você habilitará o E9-1-1 para usuários trabalhando fora da rede?**

 A aquisição automática de localização está disponível apenas para clientes localizados dentro da rede da organização, portanto, sua organização precisa decidir se dará suporte a chamadas E9-1-1 feitas de clientes Skype for Business locais. Por exemplo, você habilitará usuários para fazer chamadas de emergência se eles estiverem trabalhando de cada ou no local de um cliente? Se um cliente estiver localizado fora da rede empresarial, ele poderá ser configurado para solicitar ao usuário um local. No entanto, como esses locais fornecidos pelo usuário não podem ser pré-validados com base no MSAG (Catálogo de Endereços Principal), o despachante do provedor de serviços de emergência necessitarão confirmar a validade do local verbalmente com o chamador antes de rotear a chamada para o PSAP (ponto de atendimento público seguro).

> [!NOTE]
> Skype for Business clientes de usuários que se conectam à rede da sua organização usando VPN podem buscar informações de endereço IP internas, mas como esses endereços não podem ser usados para identificar a localização real do usuário, é essencial que as sub-redes VPN sejam excluídas do serviço informações de local.

 **Você deseja fornecer roteamento de chamada de emergência para sites fora dos EUA?**

 Talvez você queira fornecer roteamento de emergência para áreas de sua empresa que não são atendidas por um provedor de serviços de emergência (por exemplo, locais internacionais). Para fazer isso, crie um novo site e atribua políticas de voz aos sites que se referem a um uso do PSTN que roteia a chamada pelo gateway PSTN local.