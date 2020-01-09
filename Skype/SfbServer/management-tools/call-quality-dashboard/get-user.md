---
title: Obter usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: Saiba mais sobre a operação obter usuário, que faz parte do serviço de usuário. O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992618"
---
# <a name="get-user"></a>Obter usuário
 
**Resumo:** Saiba mais sobre a operação obter usuário, que faz parte do serviço de usuário. O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
A operação obter usuários faz parte do serviço de usuário na API do repositório para o painel de qualidade da chamada.
  
## <a name="get-user"></a>Obter usuário

Obter usuário retorna um registro de usuário do repositório.
  
|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<do\>portal de/QoERepositoryService/Repository/User/{userid}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros de URI** -nenhum.
  
 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.
  
 **Corpo da solicitação** -nenhum.
  
 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK). Se um ID de usuário especificado não for encontrado, ele retornará o código de status 404 (não encontrado).
  
 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.
  
 **Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userid* -ID do usuário.
  
 *LoginName* -identificação de usuário externo para usuários normais. Se a autenticação do Windows for usada para autenticar usuários, isso pode ser um FQDN do usuário.
  
 defaultidid *-ID* do item padrão para este usuário. O item padrão é o item mais alto que está associado ao usuário. Todos os outros itens que este usuário tem podem ser acessados a partir do item padrão.
  
> [!NOTE]
> Forneça o `defaultItemId` valor para obter a operação do item para recuperar os detalhes do item padrão.
  

