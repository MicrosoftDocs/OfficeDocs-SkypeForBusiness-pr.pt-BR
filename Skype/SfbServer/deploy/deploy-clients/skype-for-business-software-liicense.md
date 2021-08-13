---
title: Skype Licença de software Skype for Business Room System
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
description: Leia este tópico para saber como verificar se você tem uma licença de volume Skype for Business software.
ms.openlocfilehash: c1294df980a1fca2118e6ca2e9b172904365639900081fad7425b4d850501fdc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297607"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype Sistema de Sala: Skype for Business de software
 
Leia este tópico para saber como verificar se você tem uma licença de volume Skype for Business software. 
  
Skype O Sistema de Sala usa um cliente Skype for Business instalado, o que requer uma licença de volume de software. Antes de implantar o primeiro Skype Room System, descubra o estado de licença de volume da implantação - usando Servidores de Gerenciamento de Chaves (KMS) ou Mak (Teclas de Ativação Múltipla).
  
## <a name="key-management-servers-kms"></a>Servidores de Gerenciamento de Chaves (KMS)

Se KMS estiver no local e distribuir as Skype for Business de Licença de Volume, o Skype Room System ativará automaticamente o cliente Skype for Business. Para descobrir se KMS estão no local:
  
Em um prompt de comando, execute:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obter mais informações, consulte [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar um KMS, consulte KMS ativação do [Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) e GVLKs para KMS e ativação do [Active Directory do Office 2013](/DeployOffice/vlactivation/gvlks)
  
Office Chave de Licença de Volume Genérico 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Essa chave faz com que o sistema de sala Skype procure um KMS na rede).)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Mak (Várias Teclas de Ativação) do Centro de Serviço de Licença de Volume (VLSC)

Se o cliente usar qualquer outro software de licença de volume, o departamento de IT gerenciará as ativações de software e o Contrato de Licença de Volume (VLA) usando o VLSC. Isso também permitirá que a empresa compre ativações Skype for Business VL, após as quais a empresa poderá obter um MAK para entrada no console de administração do sistema de Skype sala.
  
Um cliente com uma VLA deve conhecer suas credenciais VLSC, que serão usadas para administrar o contrato e obter MAK. Se não tiver certeza, o departamento financeiro do cliente poderá confirmar se o cliente pagou por uma VLA.
  
Para obter um MAK, acesse o Centro de Serviço de Licenciamento por Volume para exibir contratos e baixar chaves de produto (MAK). Para obter mais informações, acesse o Centro de [Serviços de Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>MAK para Microsoft 365 ou Office 365 sem acesso VLSC

Se o cliente não tiver um Contrato de Licença de Volume, Skype for Business as ativações serão muito mais difíceis de gerenciar. No entanto, Microsoft 365 clientes Office 365 sem acesso VLSC podem obter uma MAK promocional fornecendo as seguintes informações para o OEM que vende o Skype Room System:
  
- Nome da empresa
    
- Nome de contato de implantação, email e número de telefone
    
- Número de sistemas implantados
    
- Data de implantação
    
- Se o cliente tiver um Gerenciador de Contas Técnicas da Microsoft, o nome e as informações de contato do TAM
