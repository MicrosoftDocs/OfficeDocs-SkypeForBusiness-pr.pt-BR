---
title: Solicitação de Certificado (Retornado)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'A página Status da Solicitação de Certificado Online apresenta informações importantes sobre a criação e emissão bem-sucedida da solicitação de certificado online. Essa página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção Atribuir esse certificado Skype for Business Server usos de certificados está selecionado. Se você clicar em Concluir, o certificado será atribuído automaticamente ao Lync Server 2013 para os fins que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades as quais o certificado será atribuído são:'
ms.openlocfilehash: 64c12960e574b9e43059989713974631db2a427e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831095"
---
# <a name="certificate-request-returned"></a>Solicitação de Certificado (Retornado)
 
A página **Status da Solicitação de Certificado Online** apresenta informações importantes sobre a criação e emissão bem-sucedida da solicitação de certificado online. Essa página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção **Atribuir esse certificado Skype for Business Server usos de certificados** está selecionado. Se você clicar em **Concluir**, o certificado será atribuído automaticamente ao Lync Server 2013 para os fins que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades as quais o certificado será atribuído são:
  
- Padrão do servidor para MTLS (Mutual Transport Layer Security) - conexões com clientes e outros servidores
    
- Serviços Web internos - conexões de cliente e servidor no site de serviços Web internos para Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Serviços Web externos - conexões de cliente e servidor no site de serviços Web externos para TLS/SSL
    
Clique em **Exibir detalhes do certificado** para exibir o certificado a fim de confirmar se as propriedades do certificado são o que você pretendia, e se o certificado está pronto para ser aplicado e colocado em uso no servidor.
  
Clique em **Concluir** para completar o processo de solicitação de certificado online. Se você selecionou a caixa de seleção Atribuir esse certificado **Skype for Business Server usos de certificado,** o certificado será atribuído automaticamente. Se você escolher desmarcar essa caixa de seleção, será necessário atribuir o certificado em uma etapa separada. 
  
> [!IMPORTANT]
> Se o certificado raiz da autoridade de certificação de emissão (CA) não estiver no armazenamento da Autoridade de Certificação Raiz Confiável do computador ou se os certificados de AC intermediários não estão no armazenamento adequado, você verá o status de resumo, conforme ilustrado na imagem a seguir. Você não tem a opção de atribuir o certificado. Para completar o processo de atribuição do certificado, é necessário importar o certificado raiz CA emissor e quaisquer certificados CA intermediários e atribuir o certificado clicando em **Atribuir** na página principal do Assistente de Certificado.
  

