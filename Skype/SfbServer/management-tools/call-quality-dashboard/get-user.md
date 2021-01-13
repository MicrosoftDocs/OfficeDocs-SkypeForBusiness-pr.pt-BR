---
title: Obter os Usuário
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: saiba mais sobre a operação Obter Usuário, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832411"
---
# <a name="get-user"></a>Obter os Usuário
 
**Resumo:** Saiba mais sobre a operação Obter Usuário, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
A operação Obter Usuários faz parte do Serviço de Usuário na API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="get-user"></a>Obter os Usuário

Obter Usuário retorna um registro de usuário do repositório.
  
|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|OBTER  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** - Nenhum.
  
 **Solicitação de headers** - nenhum outro.
  
 **Corpo da Solicitação** - Nenhum.
  
 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK). Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).
  
 **Response Headers** - Sem outros headers.
  
 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - ID do usuário.
  
 *loginName*  - Identificação de usuário externo para usuários regulares. Se a Autenticação do Windows for usada para autenticar usuários, esse pode ser um FQDN do usuário.
  
 *defaultItemId*  - ID do Item padrão para este usuário. O Item padrão é o item mais alto que está associado ao usuário. Todos os outros itens que este usuário possui podem ser navegados a partir do Item padrão.
  
> [!NOTE]
> Fornece o  `defaultItemId` valor da operação Obter Item para recuperar os detalhes do Item padrão.
  

