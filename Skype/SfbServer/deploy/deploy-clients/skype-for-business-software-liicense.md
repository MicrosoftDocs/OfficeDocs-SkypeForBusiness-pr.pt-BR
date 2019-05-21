---
title: Licença para software Skype for Business do sistema de sala Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business.
ms.openlocfilehash: d1d04dc6c80d4e7e04b6ed7a946dfc393a308933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287682"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de Salas do Skype: licença do software Skype for Business
 
Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business. 
  
O sistema de sala Skype usa um cliente Skype for Business instalado, que exige uma licença de volume de software. Antes de implantar o primeiro sistema de sala da Skype, descubra o estado de licenciamento por volume da implantação-usando os servidores de gerenciamento de chaves (KMS) ou as chaves de ativação múltipla (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de Gerenciamento de Chaves (KMS)

Se o KMS estiver em vigor e distribuir as ativações de licença de volume do Skype for Business, o sistema de sala do Skype ativará automaticamente o cliente Skype for Business. Para descobrir se o KMS é válido:
  
Em um prompt de comando, execute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obter mais informações, consulte [como descobrir hosts KMS do Office e do Windows via DNS e remover instâncias não autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar um KMS, consulte [ativação do kms do office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLKs para ativação do KMS e Active Directory do Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Chave de licença de volume genérica do Office 2013 para o Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (essa chave faz com que o sistema de sala do Skype procure por um KMS na rede.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Vários Chaves de Ativação (MAK) do Centro de Serviços de Licença de Volume (VLSC)

Se o cliente utilizar qualquer outro software de licença de volume, o departamento de TI gerenciará as ativações do software e o Contrato de Licença de Volume (VLA) usando o VLSC. Isso também permitirá que a empresa compre ativações VL do Skype for Business, após a qual a empresa pode obter uma MAK para entrada no console de administração do sistema da sala do Skype.
  
O cliente com um VLA deve conhecer suas credenciais VLSC, que serão utilizadas para administrar o contrato e obter o MAK. Se certeza, o departamento de finanças do cliente deve ser capaz de confirmar se o cliente pagou por uma VLA.
  
Para obter um MAK, acesse o Centro de Serviços de Licenciamento de Volume para visualizar os contratos e fazer o download das chaves de produtos (MAK). Para obter mais informações, acesse o [centro de serviços](https://www.microsoft.com/Licensing/servicecenter/default.aspx)de licenciamento por volume. 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK para o Office 365 sem acesso VLSC

Se o cliente não tiver um contrato de licença por volume, as ativações do Skype for Business serão muito mais difíceis de gerenciar. No entanto, os clientes do Office 365 sem o VLSC Access podem obter uma MAK promocional fornecendo as seguintes informações para o OEM vender o sistema de sala da Skype:
  
- Nome da empresa
    
- Nome de contato, e-mail e número de telefone para implantação
    
- Número de sistemas implantados
    
- Data da implantação
    
- Se o cliente tiver um gerente de conta técnico da Microsoft, o nome do TAM e as informações de contato
    

