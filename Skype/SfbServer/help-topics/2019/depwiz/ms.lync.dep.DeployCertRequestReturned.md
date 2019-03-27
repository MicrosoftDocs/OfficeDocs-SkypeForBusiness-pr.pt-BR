---
title: Solicitação de Certificado (Retornado)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'A página Status da solicitação de certificado Online apresenta informações importantes que resulta de êxito na criação e emissão da solicitação de certificado online. Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção atribuir esse certificado para Skype para usos de certificado de servidor de negócios está selecionada. Se você clicar em Concluir, o certificado será automaticamente atribuído para Skype para Business Server para as finalidades que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades que o certificado será atribuído são:'
ms.openlocfilehash: 70868129dc759e19960d2f6d9e3a9a1dc3d2f941
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878697"
---
# <a name="certificate-request-returned"></a>Solicitação de Certificado (Retornado)
 
A página **Status da solicitação de certificado Online** apresenta informações importantes que resulta de êxito na criação e emissão da solicitação de certificado online. Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção **atribuir este certificado Skype para usos de certificado de servidor de negócios** está selecionada. Se você clicar em **Concluir**, o certificado será automaticamente atribuído para Skype para Business Server para as finalidades que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades que o certificado será atribuído são:
  
- Padrão de servidor para Mutual Transport Layer Security (MTLS) - conexões com clientes e outros servidores
    
- Serviços Web internos - site de serviços de conexões de cliente e servidor na Web interna para Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Serviços Web externos - site de serviços de conexões de cliente e servidor na Web externa para TLS/SSL
    
Clique em **Exibir detalhes de certificados** para exibir o certificado para confirmar que as propriedades do certificado são o que você pretendia e que o certificado está pronto para ser aplicada e colocar em uso no servidor.
  
Clique em **Concluir** para concluir o processo de solicitação de certificado online. Se você marcou a caixa de seleção **atribuir este certificado Skype para usos de certificado de servidor de negócios**, o certificado será atribuído automaticamente. Se você optar por desmarcar essa caixa, você deve atribuir o certificado em uma etapa separada. 
  
> [!IMPORTANT]
> Se o certificado de raiz de autoridade de certificação emissora não estiver no repositório de autoridade de certificação raiz confiáveis do computador, ou se certificados de autoridade de certificação intermediários não estão no repositório de adequado, você verá o status de resumo, como ilustrado na imagem a seguir. Você não tem a opção para atribuir o certificado. Para concluir o processo de atribuição de certificado, você deve importar o certificado de raiz da autoridade de certificação emissora e qualquer certificados de autoridade de certificação intermediários e, em seguida, atribuir o certificado clicando em **atribuir** na página principal do Assistente de certificado.
  

