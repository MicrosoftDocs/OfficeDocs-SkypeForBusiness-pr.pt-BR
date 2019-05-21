---
title: Adicionar PSTN de Aparelho de Filial Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir o gateway PSTN (rede telefônica pública comutada) para um aparelho de ramificação sobreviventes em um site de filial, especifique o seguinte:'
ms.openlocfilehash: bd069a5bc9c8dcb4f1f787cbd436e31872bceddd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288140"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Adicionar PSTN de Aparelho de Filial Persistente
 
Para definir o gateway PSTN (rede telefônica pública comutada) para um aparelho de ramificação sobreviventes em um site de filial, especifique o seguinte: 
  
- Um FQDN (nome de domínio totalmente qualificado) ou um endereço IP para o par de gateways ao qual o aplicativo de ramificação sobreviventes ou o servidor de ramificação sobreviventes está associado para chamadas PSTN de entrada e saída.
    
    > [!IMPORTANT]
    > Se você estiver definindo um aparelho de ramificação sobreviventes, esse é o gateway ao qual o servidor de mediação dentro da ramificação de ramificação sobreviventes se conectará para conectividade PSTN. 
  
- A porta de escuta a ser usada para mensagens SIP (Session Initiation Protocol). Por padrão, as portas são a 5066 para protocolo TCP e 5067 para o protocolo TLS em um gateway, central privada de comutação telefônica (PBX) ou SBC (Session Border Controller). As portas padrão são a 5081 para TCP e 5082 para TLS em um Aparelho de Filial Persistente em um site de filial.
    
- Por motivos de segurança, recomendamos que você use o TLS. Se você estiver definindo um aparelho de ramificação sobreviventes, confira a documentação do fornecedor da sua agência de ramificação sobreviventes para verificar se o seu aparelho de ramificação sobreviventes é compatível com o protocolo TLS.
    
    > [!IMPORTANT]
    > Recomendamos, por motivos de segurança, que seja implantado um gateway que possa utilizar TLS. 
  
> [!NOTE]
> Caso deseje adicionar um gateway PSTN, você pode configurá-lo depois, porém a funcionalidade total será limitada até que o gateway PSTN seja definido e configurado. 
  

