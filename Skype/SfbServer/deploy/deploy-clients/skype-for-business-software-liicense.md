---
title: Licença de software do Skype for Business do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833921"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de Sala do Skype: licença de software do Skype for Business
 
Leia este tópico para saber como verificar se você tem uma licença de volume de software do Skype for Business. 
  
O Sistema de Sala do Skype usa um cliente do Skype for Business instalado, que requer uma licença de volume de software. Antes de implantar o primeiro Sistema de Sala do Skype, descubra o estado de licença de volume da implantação, usando KMS (Servidores de Gerenciamento de Chaves) ou Mak (Chaves de Ativação Múltipla).
  
## <a name="key-management-servers-kms"></a>Servidores de Gerenciamento de Chaves (KMS)

Se o KMS estiver em funcionamento e distribuir as ativações de Licença de Volume do Skype for Business, o Sistema de Sala do Skype ativará automaticamente o cliente Skype for Business. Para descobrir se o KMS está em operação:
  
Em um prompt de comando, execute:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obter mais informações, consulte Como descobrir hosts KMS do Office e [do Windows via DNS e remover instâncias não autorizadas.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
Para configurar um KMS, consulte a ativação KMS do [Office 2013](https://technet.microsoft.com/library/ee624357.aspx) e GVLKs para KMS e ativação do Active Directory do [Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Chave de Licença de Volume Genérica do Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Essa chave faz com que o Sistema de Sala do Skype procure por um KMS na rede).
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mak (Chaves de Ativação Múltipla) do Centro de Serviços de Licença de Volume (VLSC)

Se o cliente usar qualquer outro software de licença de volume, o departamento de IT gerenciará as ativações de software e o Contrato de Licença de Volume (VLA) usando o VLSC. Isso também permitirá que a empresa compre ativações VL do Skype for Business, após o qual a empresa poderá obter uma MAK para entrada no Console de Administração do Sistema de Sala do Skype.
  
Um cliente com um VLA deve conhecer suas credenciais VLSC, que serão usadas para administrar o contrato e obter MAK. Em caso de dúvida, o departamento financeiro do cliente deve ser capaz de confirmar se o cliente pagou por um VLA.
  
Para obter uma MAK, acesse o Centro de Serviços de Licenciamento por Volume para exibir contratos e baixar chaves de produto (MAK). Para obter mais informações, vá para o Centro de [Serviços de Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK para Microsoft 365 ou Office 365 sem acesso VLSC

Se o cliente não tiver um Contrato de Licença de Volume, as ativações do Skype for Business serão muito mais difíceis de gerenciar. No entanto, os clientes do Microsoft 365 e do Office 365 sem acesso VLSC podem obter uma MAK promocional fornecendo as seguintes informações para o OEM que vende o Sistema de Sala do Skype:
  
- Nome da empresa
    
- Nome do contato de implantação, email e número de telefone
    
- Número de sistemas implantados
    
- Data da implantação
    
- Se o cliente tiver um Gerente de Conta Técnica da Microsoft, o nome do TAM e as informações de contato
    

