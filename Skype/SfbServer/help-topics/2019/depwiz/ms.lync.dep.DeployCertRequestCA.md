---
title: Solicitação de Certificado (Autoridade de Certificação)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Ao fazer uma solicitação de certificado para uma autoridade de certificação online (CA) (normalmente, são servidores que estão em sua rede interna) na página Escolher uma Autoridade de Certificação (CA), as duas opções a seguir são apresentadas:'
ms.openlocfilehash: 8744471569c76e8f8196cda41ca398c48205fea8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830361"
---
# <a name="certificate-request-certificate-authority"></a>Solicitação de Certificado (Autoridade de Certificação)
 
Ao fazer uma solicitação de certificado para uma autoridade de certificação online (CA) (normalmente, são servidores que estão em sua rede interna) na página **Escolher uma Autoridade de Certificação (CA)**, as duas opções a seguir são apresentadas:
  
1. Selecionar um CA na lista detectada em seu ambiente.
    
2. Especificar outra autoridade de certificação.
    
Se você selecionar a primeira opção, verá uma listada que contém todas as autoridades de certificação baseadas no Windows Server detectadas em seu ambiente. Selecione a autoridade de certificação apropriada para seu certificado. Talvez seja necessário consultar seu administrador de CA para saber qual CA escolher.
  
Se você selecionar a segunda opção, digite o nome de domínio totalmente qualificado (FQDN) e a instância de CA para a autoridade de certificação que você usará para seu certificado. Essa opção será apropriada se a CA que você deseja usar não for uma CA com base no Windows Server, mas funcionará para CAs baseadas no Windows Server.
  
> [!IMPORTANT]
> Lembre-se de confirmar as associações de grupo que precisam ser bem-sucedidas com a solicitação de certificado. Normalmente, as autoridades de certificação têm um requisito de permissão diferente dos requisitos para instalar o Skype for Business Server nos servidores. Confirme os requisitos para solicitar o certificado com seu administrador de CA
. 
  

