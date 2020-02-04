---
title: Solicitação de Certificado (Retornado)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'A página status da solicitação de certificado online apresenta informações importantes resultantes da criação bem-sucedida e da emissão da solicitação de certificado online. Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção atribuir este certificado a usos de certificado do Skype for Business Server está selecionada. Se você clicar em concluir, o certificado será atribuído automaticamente ao Skype for Business Server para fins que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, os fins para os quais o certificado será atribuído são:'
ms.openlocfilehash: 0afc23baacc3430edaf1868e9fbe22e2e04455d7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705606"
---
# <a name="certificate-request-returned"></a>Solicitação de Certificado (Retornado)
 
A página **status da solicitação de certificado online** apresenta informações importantes resultantes da criação bem-sucedida e da emissão da solicitação de certificado online. Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção **atribuir este certificado a usos de certificado do Skype for Business Server** está selecionada. Se você clicar em **concluir**, o certificado será atribuído automaticamente ao Skype for Business Server para fins que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, os fins para os quais o certificado será atribuído são:
  
- Padrão do servidor para MTLS (Mutual Transport Layer Security)-conexões para clientes e outros servidores
    
- Serviços Web internos-conexões de cliente e servidor no site de serviços Web internos para segurança da camada de transporte/SSL (Secure Sockets Layer)
    
- Conexões de cliente/cliente externo de serviços Web no site de serviços Web externos para TLS/SSL
    
Clique em **Exibir detalhes do certificado** para exibir o certificado para confirmar que as propriedades do certificado são o que você pretendia e se o certificado está pronto para ser aplicado e colocado em uso no servidor.
  
Clique em **concluir** para concluir o processo de solicitação de certificado online. Se você tiver marcado a caixa de seleção **atribuir este certificado aos usos de certificado do Skype for Business Server**, o certificado será atribuído automaticamente. Se você escolheu desmarcar essa caixa de seleção, deve atribuir o certificado em uma etapa separada. 
  
> [!IMPORTANT]
> Se o certificado raiz da CA (autoridade de certificação emitente) não estiver no repositório de autoridade de certificação raiz confiável do computador ou se os certificados de autoridade de certificação intermediários não estiverem na loja apropriada, você verá o status Resumo, conforme ilustrado na imagem a seguir. Você não tem a opção de atribuir o certificado. Para concluir o processo de atribuição de certificado, você deve importar o certificado raiz da CA de emissão e qualquer certificado de CA intermediário e, em seguida, atribuir o certificado clicando em **atribuir** na página do assistente de certificado principal.
  

