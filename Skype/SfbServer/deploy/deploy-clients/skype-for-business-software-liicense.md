---
title: Licença de software do Skype Room System Skype for Business
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
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113087"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de Sala do Skype: Licença de software do Skype for Business
 
Leia este tópico para saber como verificar se você tem uma licença de volume de software do Skype for Business. 
  
O Sistema de Sala do Skype usa um cliente do Skype for Business instalado, que requer uma licença de volume de software. Antes de implantar o primeiro Sistema de Sala do Skype, descubra o estado de licença de volume da implantação - usando KMS (Key Management Servers) ou Multiple Activation Keys (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de Gerenciamento de Chaves (KMS)

Se o KMS estiver no local e distribuir as ativações da Licença de Volume do Skype for Business, o Sistema de Sala do Skype ativará automaticamente o cliente skype for Business. Para descobrir se KMS está no local:
  
Em um prompt de comando, execute:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obter mais informações, [consulte How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar um KMS, consulte [ativação KMS do Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) e [GVLKs para KMS e](/DeployOffice/vlactivation/gvlks) ativação do Active Directory do Office 2013
  
Chave de Licença de Volume Genérico do Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Essa chave faz com que o Sistema de Sala do Skype procure por um KMS na rede.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mak (Várias Teclas de Ativação) do Centro de Serviço de Licença de Volume (VLSC)

Se o cliente usar qualquer outro software de licença de volume, o departamento de IT gerenciará as ativações de software e o Contrato de Licença de Volume (VLA) usando o VLSC. Isso também permitirá que a empresa compre ativações do Skype for Business VL, após as quais a empresa poderá obter um MAK para entrada no Console de Administração do Sistema de Sala do Skype.
  
Um cliente com uma VLA deve conhecer suas credenciais VLSC, que serão usadas para administrar o contrato e obter MAK. Se não tiver certeza, o departamento financeiro do cliente poderá confirmar se o cliente pagou por uma VLA.
  
Para obter um MAK, acesse o Centro de Serviço de Licenciamento por Volume para exibir contratos e baixar chaves de produto (MAK). Para obter mais informações, acesse o Centro de [Serviços de Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK para Microsoft 365 ou Office 365 sem acesso VLSC

Se o cliente não tiver um Contrato de Licença de Volume, as ativações do Skype for Business serão muito mais difíceis de gerenciar. No entanto, os clientes do Microsoft 365 e do Office 365 sem acesso VLSC podem obter uma MAK promocional fornecendo as seguintes informações ao OEM que vende o Sistema de Sala do Skype:
  
- Nome da empresa
    
- Nome de contato de implantação, email e número de telefone
    
- Número de sistemas implantados
    
- Data de implantação
    
- Se o cliente tiver um Gerenciador de Contas Técnicas da Microsoft, o nome e as informações de contato do TAM
