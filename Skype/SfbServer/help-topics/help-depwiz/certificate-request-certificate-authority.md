---
title: Solicitação de Certificado (Autoridade de Certificação)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Quando você faz uma solicitação de certificado para uma CA (autoridade de certificação online) (normalmente, esses são os servidores que estão em sua rede interna) na página Escolher uma autoridade de certificação (CA), são apresentadas duas opções:'
ms.openlocfilehash: 6fea8ba9500e1612ff13796f4c58550687baa99a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-certificate-authority"></a>Solicitação de Certificado (Autoridade de Certificação)
 
Ao fazer uma solicitação de certificado para uma autoridade de certificação online (AC) (normalmente, servidores que estão em sua rede interna) na página **Escolher uma Autoridade de Certificação (AC)**, as duas opções a seguir são apresentadas:
  
1. Selecionar uma AC na lista detectada em seu ambiente.
    
2. Especificar outra autoridade de certificação.
    
Se você selecionar a primeira opção, você verá uma lista suspensa que contém todas as autoridades de certificação baseada no Windows Server detectados no seu ambiente. Selecione a autoridade de certificação apropriada para seu certificado. Talvez seja necessário consultar o administrador de AC para saber qual AC escolher.
  
Se você selecionar a segunda opção, digite o nome de domínio totalmente qualificado (FQDN) e a instância de AC da autoridade de certificação que você usará para o seu certificado. Essa opção será apropriada se a AC que você deseja usar não for uma AC baseada no Windows Server, mas funcionará para ACs baseadas no Windows Server.
  
> [!IMPORTANT]
> Lembre-se de confirmar as associações de grupo que precisam ser bem-sucedidas com a solicitação de certificado. Geralmente, as autoridades de certificação têm um requisito de permissão diferentes dos requisitos de instalação Skype para Business Server nos servidores. Confirme os requisitos para solicitar o certificado com seu administrador de AC. 
  

