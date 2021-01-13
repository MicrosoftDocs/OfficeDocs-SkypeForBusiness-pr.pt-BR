---
title: Solicitação de Certificado (Retornado)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'A página Status da Solicitação de Certificado Online apresenta informações importantes sobre a criação e emissão bem-sucedida da solicitação de certificado online. Essa página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção Atribuir este certificado a usos de certificados do Skype for Business Server está marcada. Se você clicar em Concluir, o certificado será atribuído automaticamente ao Skype for Business Server para as finalidades definidas durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades as quais o certificado será atribuído são:'
ms.openlocfilehash: 8d7d1dc5013505b7874bccd2ee415f9211713e70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801831"
---
# <a name="certificate-request-returned"></a>Solicitação de Certificado (Retornado)
 
A página **Status da Solicitação de Certificado Online** apresenta informações importantes sobre a criação e emissão bem-sucedida da solicitação de certificado online. Essa página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção Atribuir este certificado a usos de **certificados do Skype for Business Server** está marcada. Se você clicar **em Concluir,** o certificado será atribuído automaticamente ao Skype for Business Server para as finalidades definidas durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades as quais o certificado será atribuído são:
  
- Padrão do servidor para MTLS (Mutual Transport Layer Security) - Conexões com clientes e outros servidores
    
- Serviços Web internos - Conexões de cliente e servidor no site de serviços Web internos para Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Serviços Web externos - Conexões de cliente e servidor no site de serviços Web externos para TLS/SSL
    
Clique em **Exibir detalhes do certificado** para exibir o certificado a fim de confirmar se as propriedades do certificado são o que você pretendia, e se o certificado está pronto para ser aplicado e colocado em uso no servidor.
  
Clique em **Concluir** para completar o processo de solicitação de certificado online. Se você selecionou a caixa de seleção Atribuir este certificado aos usos de certificados do **Skype for Business Server,** o certificado será atribuído automaticamente. Se você escolher desmarcar essa caixa de seleção, será necessário atribuir o certificado em uma etapa separada. 
  
> [!IMPORTANT]
> Se o certificado raiz da autoridade de certificação (CA) de emissão não estiver no armazenamento da Autoridade de Certificação Raiz Confiável do computador ou se os certificados ca intermediários não estão no armazenamento apropriado, você verá o status do resumo, conforme ilustrado na imagem a seguir. Você não tem a opção de atribuir o certificado. Para completar o processo de atribuição do certificado, é necessário importar o certificado raiz CA emissor e quaisquer certificados CA intermediários e atribuir o certificado clicando em **Atribuir** na página principal do Assistente de Certificado.
  

