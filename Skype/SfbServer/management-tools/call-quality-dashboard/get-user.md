---
title: Obter os Usuário
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: saiba mais sobre a operação Obter Usuário, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: adcb832d03d97eee978e3eb4c0f9027bd44ac7ce
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768669"
---
# <a name="get-user"></a>Obter os Usuário
 
**Resumo:** Saiba mais sobre a operação Obter Usuário, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
A operação Get Users faz parte do Serviço de Usuário na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-user"></a>Obter os Usuário

Get User retorna um registro de usuário do repositório.
  
|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - Nenhum.
  
 **Headers de solicitação** - Sem headers adicionais.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
 **Headers de resposta** - Sem headers adicionais.
  
 **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - ID do usuário.
  
 *loginName*  - Identificação de usuário externo para usuários regulares. Se Windows Autenticação for usada para autenticação de usuários, isso pode ser um FQDN do usuário.
  
 *defaultItemId*  - ID do Item padrão para este usuário. O Item padrão é o item mais alto que está associado ao usuário. Todos os outros itens que esse usuário possui podem ser navegados a partir do Item padrão.
  
> [!NOTE]
> Fornece o  `defaultItemId` valor à operação Obter Item para recuperar os detalhes do Item padrão.
  

