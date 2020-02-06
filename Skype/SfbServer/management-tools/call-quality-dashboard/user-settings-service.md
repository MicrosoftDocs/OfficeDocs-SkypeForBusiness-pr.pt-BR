---
title: Serviço de configurações do usuário para o painel de qualidade de chamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumo: Saiba mais sobre o serviço configurações do usuário, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816640"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Serviço de configurações do usuário para o painel de qualidade de chamada (CQD)
 
**Resumo:** Saiba mais sobre o serviço configurações do usuário, que faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada.
  
## <a name="user-settings-service"></a>Serviço de configurações de usuário

As configurações de usuário são pares de valor chave que os aplicativos podem usar para armazenar metadados para várias finalidades, incluindo a personalização de comportamentos do aplicativo por usuário. Cada usuário recebe um armazenamento de configurações de usuário. Somente os proprietários podem adicionar, modificar e remover as configurações do usuário.
  
 **Configurações globais**
  
As configurações globais são as configurações de usuário pertencentes ao usuário do sistema e todos os usuários têm acesso somente leitura a elas. As configurações globais são constantes: elas são criadas durante a criação do repositório e nunca mudam.
  
Cada usuário pode substituir as configurações globais criando configurações de usuário com as mesmas chaves. Quando o aplicativo solicita as configurações de usuário efetivas, a API retorna um conjunto de configurações globais mescladas com as configurações de usuário, com cada configuração de usuário substituindo a respectiva configuração global se as chaves forem iguais. A API também pode retornar apenas as configurações do usuário para que os aplicativos possam descobrir quais configurações são substituídas. 
  
As operações REST estão incluídas na tabela a seguir.

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter configurações de usuário](get-user-settings.md) <br/> |Obter configurações do usuário retorna uma lista de configurações para um usuário especificado.  <br/> |
|[Obter configuração de usuário](get-user-setting.md) <br/> |Obter configuração de usuário retorna uma única configuração de usuário.  <br/> |
   

