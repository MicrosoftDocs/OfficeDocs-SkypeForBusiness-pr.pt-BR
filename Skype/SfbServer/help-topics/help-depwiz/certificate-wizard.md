---
title: Assistente de Certificado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Para Solicitar, Atribuir, Remover ou Exibir certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (AC) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado da infraestrutura de chave pública (PKI) da sua organização, você precisa confirmar o que será adicional, se for o caso, você precisará de associações de grupo. Durante a tarefa de solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão da sua PKI.
ms.openlocfilehash: f37b4edae379ac96bc8b4854da891ef223192fa4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823755"
---
# <a name="certificate-wizard"></a>Assistente de Certificado
 
Para **Solicitar**, **Atribuir**, **Remover** ou **Exibir** certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (AC) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado da infraestrutura de chave pública (PKI) da sua organização, você precisa confirmar o que será adicional, se for o caso, você precisará de associações de grupo. Durante a tarefa de solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão da sua PKI.
  
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
> **Importar Certificado** é normalmente usado para processar um certificado recebido por meio de um processo diferente de uma solicitação do Assistente de Certificado. Por exemplo, seu administrador de PKI cria um certificado e o disponibiliza a você. Use **importar certificado** para importar o certificado para o repositório de certificados do computador e torná-lo disponível para o Skype for Business Server atribuir.
  
Para completar o processo de solicitação de uma solicitação de certificado de uma AC em sua organização que exige aprovação do administrador de AC, clique em **Processar Solicitação Pendente**. A solicitação de certificado retornará um status de pendente e também exibirá o número de identificação da solicitação pendente. Para continuar processando um certificado com um status de pendente, clique em **Atualizar** para habilitar o botão **Processar Solicitação Pendente**. O botão **Processar Solicitação Pendente** não ficará mais indisponível (esmaecido). Dessa forma, é possível tentar recuperar a solicitação pendente, mas o status da solicitação permanecerá pendente até que o certificado seja emitido ou negado pelo administrador da AC. O botão ficará indisponível se não houver solicitações pendentes válidas criadas pelo Assistente de Certificado.
  

