---
title: User Configurações Service for Call Quality Dashboard (CQD)
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumo: saiba mais sobre o Serviço Configurações usuário, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: c037024c8fe336c3614dd9daf6ee02370337ad5c6c44b45c783044cc421f626f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315557"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>User Configurações Service for Call Quality Dashboard (CQD)
 
**Resumo:** Saiba mais sobre o Serviço Configurações usuário, que faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.
  
O Serviço Configurações usuário faz parte da API de Repositório para Painel de Qualidade de Chamada.
  
## <a name="user-settings-service"></a>Serviço de Configurações de Usuário

As configurações do usuário são pares de valores-chave que os aplicativos podem usar para armazenar metadados para várias finalidades, incluindo personalização de comportamentos de aplicativos por usuário. Cada usuário recebe um armazenamento para configurações do usuário. Somente os proprietários podem adicionar, modificar e remover configurações do usuário.
  
 **Global Configurações**
  
As configurações globais são as configurações do usuário pertencentes ao usuário do sistema e todos os usuários têm acesso somente leitura a eles. As configurações globais são constantes: elas são criadas durante a criação do repositório e nunca mudam.
  
Cada usuário pode substituir as configurações globais criando configurações do usuário com as mesmas chaves. Quando o aplicativo solicita as configurações efetivas do usuário, a API retorna um conjunto de configurações globais mescladas com as configurações do usuário, com cada configuração do usuário sobressando a configuração global respectiva se as chaves são as mesmas. A API também pode retornar apenas as configurações do usuário para que os aplicativos possam descobrir quais configurações são substituidas. 
  
As operações REST estão incluídas na tabela a seguir.

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter configurações de usuário](get-user-settings.md) <br/> |Get User Configurações retorna uma lista de configurações para um usuário especificado.  <br/> |
|[Obter configuração de usuário](get-user-setting.md) <br/> |Obter Configuração do Usuário retorna uma única configuração de usuário.  <br/> |
   

