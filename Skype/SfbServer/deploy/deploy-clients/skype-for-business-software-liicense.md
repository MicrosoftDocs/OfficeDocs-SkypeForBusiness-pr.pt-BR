---
title: Skype sala sistema Skype para a licença do software de negócios
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business.
ms.openlocfilehash: 8bc8abfb4b379faaf94ac8cf8fbf4fdb792329bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893338"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de Salas do Skype: licença do software Skype for Business
 
Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business. 
  
Sistema de sala do Skype usa um Skype instalado para cliente corporativos, que requer uma licença de volume do software. Antes de implantar o sistema de sala Skype primeiro, descubra o estado da licença de volume da implantação - usando servidores de gerenciamento de chaves (KMS) ou chaves de ativação múltipla (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de Gerenciamento de Chaves (KMS)

Se KMS estão funcionando e distribuirá Skype para ativações de licença de Volume de negócios, o sistema de sala Skype ativa automaticamente o Skype para o cliente de negócios. Para descobrir se o KMS é válido:
  
No prompt de comando, execute:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obter mais informações, consulte [como descobrir o Office e o KMS do Windows hosts por meio de DNS e remova as instâncias não autorizadas](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar um KMS, consulte [ativação do KMS do Office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLKs para ativação KMS and Active Directory do Office 2013](https://technet.microsoft.com/library/dn385360.aspx)
  
Chave de licença de Volume do Office 2013 genérico para o Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (essa chave faz com que o sistema de sala Skype procurar um KMS na rede.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Vários Chaves de Ativação (MAK) do Centro de Serviços de Licença de Volume (VLSC)

Se o cliente utilizar qualquer outro software de licença de volume, o departamento de TI gerenciará as ativações do software e o Contrato de Licença de Volume (VLA) usando o VLSC. Isso também permitirá a empresa adquirir Skype para ativações VL de negócios, após o qual a empresa pode obter uma chave MAK para entrada no Console de administração do sistema Skype sala.
  
O cliente com um VLA deve conhecer suas credenciais VLSC, que serão utilizadas para administrar o contrato e obter o MAK. Se estiver em dúvida, departamento de finanças do cliente deve ser capaz de confirmar se o cliente pagou para um VLA.
  
Para obter um MAK, acesse o Centro de Serviços de Licenciamento de Volume para visualizar os contratos e fazer o download das chaves de produtos (MAK). Para obter mais informações, vá para o [Centro de atendimento de licenciamento por Volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK para o Office 365 sem acesso VLSC

Se o cliente não tiver um contrato de licença de Volume, Skype para ativações de negócios será muito mais difícil de gerenciar. No entanto, os clientes do Office 365 sem acesso ao VLSC podem obter uma MAK promocional, fornecendo as seguintes informações ao OEM vendendo o sistema de sala Skype:
  
- Nome da empresa
    
- Nome de contato, e-mail e número de telefone para implantação
    
- Número de sistemas implantados
    
- Data da implantação
    
- Se o cliente tiver um Microsoft gerente técnico da conta, nome e informações de contato do TAM
    

