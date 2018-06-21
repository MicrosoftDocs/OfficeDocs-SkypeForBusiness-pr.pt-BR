---
title: Adicionar PSTN de Aparelho de Filial Persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Para definir o gateway PSTN (rede) telefônica comutada pública para um aparelho de filial persistente em um site de filial, especifique o seguinte:'
ms.openlocfilehash: 7357beacc93e9fbfede068802c5e849416096a0e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19996881"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Adicionar PSTN de Aparelho de Filial Persistente
 
Para definir o gateway PSTN (rede) telefônica comutada pública para um aparelho de filial persistente em um site de filial, especifique o seguinte: 
  
- Um nome de domínio totalmente qualificado (FQDN) ou o endereço IP para o par de gateway que o aparelho de filial persistente ou servidor de filial persistente está associado para roteamento de entrada e saída chamadas PSTN.
    
    > [!IMPORTANT]
    > Se você estiver definindo um aparelho de filial persistente, este é o gateway ao qual o servidor de mediação dentro do aparelho de filial persistente se conectará para conectividade PSTN. 
  
- A porta de escuta a ser usada para mensagens SIP (Session Initiation Protocol). Por padrão, as portas são a 5066 para protocolo TCP e 5067 para o protocolo TLS em um gateway, central privada de comutação telefônica (PBX) ou SBC (Session Border Controller). As portas padrão são a 5081 para TCP e 5082 para TLS em um Aparelho de Filial Persistente em um site de filial.
    
- Por motivos de segurança, recomendamos que você use o TLS. Se você estiver definindo um aparelho de filial persistente, consulte a documentação do fornecedor de aparelho de filial persistente para verificar se o seu aparelho de filial persistente suporta o protocolo TLS.
    
    > [!IMPORTANT]
    > Recomendamos, por motivos de segurança, que seja implantado um gateway que possa utilizar TLS. 
  
> [!NOTE]
> Caso deseje adicionar um gateway PSTN, você pode configurá-lo depois, porém a funcionalidade total será limitada até que o gateway PSTN seja definido e configurado. 
  

