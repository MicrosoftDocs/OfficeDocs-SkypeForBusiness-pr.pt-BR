---
title: Assistente de Certificado
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: Para Solicitar, Atribuir, Remover ou Exibir certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (CA) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado da PKI (infraestrutura de chave pública) da sua organização, você precisa confirmar quais associações de grupo adicionais, se alguma, você precisará. Durante a tarefa Solicitar, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão do PKI.
ms.openlocfilehash: 7b5776de91b814b289f28b86c38f29e3a35e54c6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738777"
---
# <a name="certificate-wizard"></a>Assistente de Certificado
 
Para **Solicitar**, **Atribuir**, **Remover** ou **Exibir** certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (CA) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado da PKI (infraestrutura de chave pública) da sua organização, você precisa confirmar quais associações de grupo adicionais, se alguma, você precisará. Durante a tarefa Solicitar, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão do PKI.
  
Para solicitar um novo certificado, clique em **Solicitar**.
  
Para atribuir um certificado que ainda não foi atribuído, clique em **Atribuir**.
  
Para remover um certificado atribuído anteriormente, clique em **Remover**.
  
> [!NOTE]
> O botão **Remover** estará disponível somente se um certificado tiver sido atribuído anteriormente. Se o botão **Remover** não estiver disponível (esmaecido), não haverá certificado atribuído.
  
Para exibir um certificado atribuído, clique em **Exibir**.
  
> [!NOTE]
> O botão **Exibir** estará disponível somente se um certificado tiver sido atribuído anteriormente. Se o botão **Exibir** estiver escurecido, não haverá certificado atribuído.
  
Para atualizar a tela de atribuição de certificado atual, clique em **Atualizar**.
  
Para importar um certificado que não está presente no repositório de certificados, clique em **Importar Certificado**.
  
> [!NOTE]
> **Importar Certificado** é normalmente usado para processar um certificado recebido por meio de um processo diferente de uma solicitação do Assistente de Certificado. Por exemplo, seu administrador de PKI cria um certificado e o disponibiliza a você. Use **Importar Certificado** para importar o certificado para o armazenamento de certificados do computador e torná-lo disponível para Skype for Business Server atribuir.
  
Para completar o processo de solicitação de uma solicitação de certificado de uma CA em sua organização que exige aprovação do administrador de CA, clique em **Processar Solicitação Pendente**. A solicitação de certificado retornará um de pendente e também exibirá o número de identificação da solicitação pendente. Para continuar processando um certificado com um status de pendente, clique em **Atualizar** para habilitar o botão **Processar Solicitação Pendente**. O botão **Processar Solicitação Pendente** não ficará mais indisponível (esmaecido). Dessa forma, é possível tentar recuperar a solicitação pendente, mas o status da solicitação permanecerá pendente até que o certificado seja emitido ou negado pelo administrador de CA. O botão ficará indisponível se não houver solicitações pendentes válidas criadas pelo Assistente de Certificado.
  

