---
title: Solicitação de Certificado (Autoridade de Certificação)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Ao fazer uma solicitação de certificado para uma autoridade de certificação online (CA) (normalmente, são servidores que estão em sua rede interna) na página Escolher uma Autoridade de Certificação (CA), as duas opções a seguir são apresentadas:'
---

# <a name="certificate-request-certificate-authority"></a>Solicitação de Certificado (Autoridade de Certificação)
 
Ao fazer uma solicitação de certificado para uma autoridade de certificação online (CA) (normalmente, são servidores que estão em sua rede interna) na página **Escolher uma Autoridade de Certificação (CA)**, as duas opções a seguir são apresentadas:
  
1. Selecionar um CA na lista detectada em seu ambiente.
    
2. Especificar outra autoridade de certificação.
    
Se você selecionar a primeira opção, verá uma listada que contém todas as Windows de certificação baseadas em servidor detectadas em seu ambiente. Selecione a autoridade de certificação apropriada para seu certificado. Talvez seja necessário consultar seu administrador de CA para saber qual CA escolher.
  
Se você selecionar a segunda opção, digite o nome de domínio totalmente qualificado (FQDN) e a instância de CA para a autoridade de certificação que você usará para seu certificado. Essa opção será apropriada se a CA que você deseja usar não for uma CA com base no Windows Server, mas funcionará para CAs baseadas no Windows Server.
  
> [!IMPORTANT]
> Lembre-se de confirmar as associações de grupo que precisam ser bem-sucedidas com a solicitação de certificado. Normalmente, as autoridades de certificação têm um requisito de permissão diferente dos requisitos para instalar Skype for Business Server em servidores. Confirme os requisitos para solicitar o certificado com seu administrador de CA
. 
  

