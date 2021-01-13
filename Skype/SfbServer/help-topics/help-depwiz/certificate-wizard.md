---
title: Assistente de Certificado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Para Solicitar, Atribuir, Remover ou Exibir certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (CA) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado da PKI (infraestrutura de chave pública) da sua organização, você precisa confirmar quais associações de grupo adicionais, se alguma, serão necessários. Durante a tarefa De solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão da PKI.
ms.openlocfilehash: f8c21cf141d2145e7592a0615a32eafdfa8de10e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805081"
---
# <a name="certificate-wizard"></a>Assistente de Certificado
 
Para **Solicitar**, **Atribuir**, **Remover** ou **Exibir** certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (CA) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado da PKI (infraestrutura de chave pública) da sua organização, você precisa confirmar quais associações de grupo adicionais, se alguma, serão necessários. Durante a tarefa De solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão da PKI.
  
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
> **Importar Certificado** é normalmente usado para processar um certificado recebido por meio de um processo diferente de uma solicitação do Assistente de Certificado. Por exemplo, seu administrador de PKI cria um certificado e o disponibiliza a você. Use **Importar Certificado** para importar o certificado para o armazenamento de certificados do computador e torná-lo disponível para o Skype for Business Server atribuir.
  
Para completar o processo de solicitação de uma solicitação de certificado de uma CA em sua organização que exige aprovação do administrador de CA, clique em **Processar Solicitação Pendente**. A solicitação de certificado retornará um de pendente e também exibirá o número de identificação da solicitação pendente. Para continuar processando um certificado com um status de pendente, clique em **Atualizar** para habilitar o botão **Processar Solicitação Pendente**. O botão **Processar Solicitação Pendente** não ficará mais indisponível (esmaecido). Dessa forma, é possível tentar recuperar a solicitação pendente, mas o status da solicitação permanecerá pendente até que o certificado seja emitido ou negado pelo administrador de CA. O botão ficará indisponível se não houver solicitações pendentes válidas criadas pelo Assistente de Certificado.
  

