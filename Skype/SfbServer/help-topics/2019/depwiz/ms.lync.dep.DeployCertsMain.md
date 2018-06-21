---
title: Assistente de Certificado
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Para solicitar, atribuir, remover ou exibir certificados, você deve usar o Assistente de certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (AC) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado de infraestrutura de chave pública (PKI) de sua organização, será necessário confirmar o que adicionais — se houver — você precisará de associações de grupo. Durante a tarefa de solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar que o certificado em sua PKI emissão da autoridade de certificação.
ms.openlocfilehash: 5216b190aafc095f00cd66e931c84caebd115a69
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19997035"
---
# <a name="certificate-wizard"></a>Assistente de Certificado
 
Para **Solicitar**, **Atribuir**, **Remover** ou **Exibir** certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (AC) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado de infraestrutura de chave pública (PKI) de sua organização, será necessário confirmar o que adicionais — se houver — você precisará de associações de grupo. Durante a tarefa de solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar que o certificado em sua PKI emissão da autoridade de certificação.
  
Para solicitar um novo certificado, clique em **Solicitar**.
  
Para atribuir um certificado que ainda não foi atribuído, clique em **Atribuir**.
  
Para remover um certificado atribuído anteriormente, clique em **Remover**.
  
> [!NOTE]
> O botão **Remover** estará disponível somente se um certificado tiver sido atribuído anteriormente. Se o botão **Remover** não estiver disponível (esmaecido), então não há certificado atribuído.
  
Para exibir um certificado atribuído, clique em **Exibir**.
  
> [!NOTE]
> O botão **Exibir** estará disponível somente se um certificado tiver sido atribuído anteriormente. Se o botão **Exibir** estiver esmaecido, então não há certificado atribuído.
  
Para atualizar a tela atual de atribuição de certificado, clique em **Atualizar**.
  
Para importar um certificado que não está presente no repositório de certificados, clique em **Importar Certificado**.
  
> [!NOTE]
> **Importar Certificado** é normalmente usado para processar um certificado recebido por meio de um processo diferente de uma solicitação do Assistente de Certificado. Por exemplo, seu administrador de PKI cria um certificado e o disponibiliza a você. Uso de **Importar o certificado** para importar o certificado para o certificado do computador armazenar e disponibilizá-lo para Skype para Business Server atribuir.
  
Para completar o processo de solicitação de uma solicitação de certificado de uma AC em sua organização que exige aprovação do administrador de AC, clique em **Processar Solicitação Pendente**. A solicitação de certificado retornará um status de pendente e também exibirá o número de identificação da solicitação pendente. Para continuar processando um certificado com um status de pendente, clique em **Atualizar** para habilitar o botão **Processar Solicitação Pendente**. O botão **Processar Solicitação Pendente** não ficará mais indisponível (esmaecido). Dessa forma, é possível tentar recuperar a solicitação pendente, mas o status da solicitação permanecerá pendente até que o certificado seja emitido ou negado pelo administrador da AC. O botão ficará indisponível se não houver solicitações pendentes válidas criadas pelo Assistente de Certificado.
  

