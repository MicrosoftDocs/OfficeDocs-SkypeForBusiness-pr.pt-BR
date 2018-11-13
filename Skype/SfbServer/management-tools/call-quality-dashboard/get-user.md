---
title: Obter do usuário
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: Saiba mais sobre a operação de usuário obter, que faz parte do serviço de usuário. O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: e562cbc1bf81a231eaff162cd073512a08365bf6
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295973"
---
# <a name="get-user"></a>Obter do usuário
 
**Resumo:** Saiba mais sobre a operação de usuário obter, que faz parte do serviço de usuário. O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
A operação obter usuários é parte do serviço do usuário na API repositório para o painel de controle de qualidade de chamada.
  
## <a name="get-user"></a>Obter do usuário

Obtenha o usuário retornos de um registro de usuário do repositório.
  
|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Obter  <br/> |https://\<portal\>/QoERepositoryService/repositório/usuário / {userId}  <br/> |HTTP/1.1  <br/> |
   
 **Parâmetros URI** - None.
  
 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.
  
 O **corpo da solicitação** - None.
  
 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.
  
 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey). Se um usuário especificado que ID não for encontrado, será retornado o código de status 404 (não encontrado).
  
 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.
  
 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId* - ID do usuário.
  
 *loginName* - identificação de usuário externo para usuários regulares. Se a autenticação do Windows é usada para autenticação de usuários, isso pode ser um FQDN do usuário.
  
 *defaultItemId* - ID do Item padrão para este usuário. O Item padrão é o Item de nível superior que está associado ao usuário. Todos os outros itens que pertencentes este usuário podem ser navegados para o Item padrão.
  
> [!NOTE]
> Fornecer o `defaultItemId` valor a operação obter Item para recuperar os detalhes do Item padrão.
  

