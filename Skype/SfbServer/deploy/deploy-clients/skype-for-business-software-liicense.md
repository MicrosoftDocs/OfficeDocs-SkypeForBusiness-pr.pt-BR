---
title: 'Sistema de Salas do Skype: licença do software Skype for Business'
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business.
ms.openlocfilehash: e91a009c29647031d91e791ba5fd41ccc4578d1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Sistema de Salas do Skype: licença do software Skype for Business
 
Leia este tópico para saber como verificar se você tem uma licença de volume do software Skype for Business. 
  
Skype Room System uses an installed Skype for Business client, which requires a software volume license. Antes de implantar o primeiro , descubra o estado de licença de volume da implantação - utilizando os Servidores de Gerenciamento de Chaves (KMS) ou várias Chaves de Ativação (MAK).
  
## <a name="key-management-servers-kms"></a>Servidores de Gerenciamento de Chaves (KMS)

If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client. Para descobrir se o KMS é válido:
  
A partir de um prompt de comando, execute: `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
Para obter mais informações, consulte [Como descobrir os hosts de KMS do Office e do Windows via DNS e remover instâncias não autorizadashttp://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx). 
  
Para configurar um KMS, consultar [Ativação do KMS do Office 2013https://technet.microsoft.com/pt-br/library/ee624357.aspx](https://technet.microsoft.com/en-us/library/ee624357.aspx) e [GVLKs para ativação do KMS e do Active Directory do Office 2013https://technet.microsoft.com/pt-br/library/dn385360.aspx](https://technet.microsoft.com/en-us/library/dn385360.aspx)
  
Chave Genérica da Licença de Volume do Office 2013 para Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Esta chave faz com que o  procure um KMS na rede.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>Vários Chaves de Ativação (MAK) do Centro de Serviços de Licença de Volume (VLSC)

Se o cliente utilizar qualquer outro software de licença de volume, o departamento de TI gerenciará as ativações do software e o Contrato de Licença de Volume (VLA) usando o VLSC. Isto também permitirá à empresa adquirir as ativações VL do , além de obter um MAK para sua entrada no Console de Administração do .
  
O cliente com um VLA deve conhecer suas credenciais VLSC, que serão utilizadas para administrar o contrato e obter o MAK. Em caso de dúvida, o departamento financeiro do cliente deve confirmar se o cliente pagou por um VLA.
  
Para obter um MAK, acesse o Centro de Serviços de Licenciamento de Volume para visualizar os contratos e fazer o download das chaves de produtos (MAK). Para obter mais informações, acesse [Centro de Serviços de Licenciamento de Volumehttps://www.microsoft.com/Licensing/servicecenter/default.aspx](https://www.microsoft.com/Licensing/servicecenter/default.aspx). 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>MAK para o Office 365 sem acesso VLSC

Se o cliente não tiver um Contrato de Licença de Volume, as ativações do serão muito mais difíceis de gerenciar. No entanto, os clientes do Office 365 sem acesso a VLSC podem obter um MAK promocional fornecendo as informações a seguir para o OEM que estiver vendendo o :
  
- Nome da empresa
    
- Nome de contato, e-mail e número de telefone para implantação
    
- Número de sistemas implantados
    
- Data da implantação
    
- Se o cliente tiver um Gerente de Conta Técnico da Microsoft, fornecer o nome e informações de contato do TAM
    

