---
title: Adicionar Aparelho PSTN a Filial Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir o gateway da rede telefônica pública comutada (PSTN) para um Aparelho de Filial Persistente de um local de filial, especifique o seguinte:'
ms.openlocfilehash: 30b5922e3d18b4dfe57bef23ddb0f00a25df7f9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811941"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Adicionar Aparelho PSTN a Filial Persistente
 
Para definir o gateway da rede telefônica pública comutada (PSTN) para um Aparelho de Filial Persistente de um local de filial, especifique o seguinte: 
  
- Um FQDN (nome de domínio totalmente qualificado) ou endereço IP para o par de gateway ao qual o Aparelho de Filial Persistente ou Servidor de Filial Persistente está associado, para roteamento de chamadas PSTN de entrada e saída.
    
    > [!IMPORTANT]
    > Se você está definindo um Aparelho de Filial Persistente, este é o gateway ao qual o Servidor de Mediação dentro do Aparelho de Filial Persistente se conectará para obter conectividade PSTN. 
  
- A porta de escuta a ser usada para mensagens SIP (Session Initiation Protocol). Por padrão, as portas são a 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security) em um gateway, PBX (private branch exchange) ou SBC (Session Border Controller). As portas padrão são a 5081 para TCP e 5082 para TLS em um Aparelho de Filial Persistente em um site de filial.
    
- Recomendamos que utilize TLS por razões de segurança. Caso esteja definindo um Aparelho de Filial Persistente, consulte sua documentação do fornecedor do Aparelho de Filial Persistente para verificar se o seu Aparelho de Filial Persistente é compatível com protocolo TLS.
    
    > [!IMPORTANT]
    > Recomendamos, por motivos de segurança, que seja implantado um gateway que possa utilizar TLS. 
  
> [!NOTE]
> Caso deseje adicionar um gateway PSTN, você pode montá-lo mais tarde porém a funcionalidade total será limitada até que o gateway PSTN seja definido e configurado. 
  

