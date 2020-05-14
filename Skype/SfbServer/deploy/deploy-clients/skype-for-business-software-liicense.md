---
title: Licença de software do Skype for Business do sistema de salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leia este tópico para saber como verificar se você tem uma licença de volume de software do Skype for Business.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220921"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de salas do Skype: licença de software do Skype for Business
 
Leia este tópico para saber como verificar se você tem uma licença de volume de software do Skype for Business. 
  
O sistema de salas do Skype usa um cliente do Skype for Business instalado, que requer uma licença de volume do software. Antes de implantar o primeiro sistema de sala do Skype, descubra o estado de licença de volume da implantação – usando os servidores de gerenciamento de chaves (KMS) ou várias chaves de ativação (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de gerenciamento de chaves (KMS)

Se o KMS estiver em vigor e distribuirá as ativações de licença de volume do Skype for Business, o sistema de salas do Skype ativará automaticamente o cliente Skype for Business. Para descobrir se o KMS está no local:
  
A partir de um prompt de comando, execute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obter mais informações, consulte [como descobrir hosts KMS do Office e do Windows via DNS e remover instâncias não autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar um KMS, confira [ativação do kms do office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLKs para ativação do KMS e do Active Directory do Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Chave genérica de licença de volume do Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (esta chave faz com que o sistema de salas do Skype procure um KMS na rede.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Chaves de ativação múltipla (MAK) do centro de serviços de licenciamento por volume (VLSC)

Se o cliente usar qualquer outro software de licença de volume, o departamento de ti gerenciará as ativações de software e o contrato de licença de volume (VLA) usando o VLSC. Isso também permitirá que a empresa adquira as ativações VL do Skype for Business, após a qual a empresa pode obter uma MAK para entrada no console de administração do sistema de salas do Skype.
  
Um cliente com um VLA deve conhecer suas credenciais do VLSC, que serão usadas para administrar o contrato e obter a MAK. Se certeza, o departamento financeiro do cliente deve ser capaz de confirmar se o cliente pagou por um VLA.
  
Para obter uma MAK, acesse o centro de serviços de licenciamento por volume para exibir contratos e baixar chaves do produto (MAK). Para obter mais informações, vá para o [centro de serviços de licenciamento por volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK para o Microsoft 365 ou o Office 365 sem acesso VLSC

Se o cliente não tiver um contrato de licença por volume, as ativações do Skype for Business serão muito mais difíceis de gerenciar. No entanto, os clientes do Microsoft 365 e do Office 365 sem o VLSC Access podem obter uma MAK promocional fornecendo as seguintes informações ao OEM vendendo o sistema de salas do Skype:
  
- Nome da empresa
    
- Nome do contato, email e número de telefone da implantação
    
- Número de sistemas implantados
    
- Data de implantação
    
- Se o cliente tiver um gerente de conta técnico da Microsoft, o nome do TAM e as informações de contato
    

