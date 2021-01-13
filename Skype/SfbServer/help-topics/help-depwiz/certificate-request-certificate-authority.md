---
title: Solicitação de Certificado (Autoridade de Certificação)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Ao fazer uma solicitação de certificado para uma autoridade de certificação online (CA) (normalmente, são servidores que estão em sua rede interna) na página Escolher uma Autoridade de Certificação (CA), as duas opções a seguir são apresentadas:'
ms.openlocfilehash: 0081ab852a1650dfafd61471891a002be60def3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805321"
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
  

