---
title: Serviço de Configurações do Usuário para o Painel de Qualidade da Chamada (CQD)
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
description: 'Resumo: saiba mais sobre o Serviço de Configurações do Usuário, que faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803032"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Serviço de Configurações do Usuário para o Painel de Qualidade da Chamada (CQD)
 
**Resumo:** Saiba mais sobre o Serviço de Configurações do Usuário, que faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.
  
O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada.
  
## <a name="user-settings-service"></a>Serviço de Configurações de Usuário

As configurações do usuário são pares chave-valor que os aplicativos podem usar para armazenar metadados para várias finalidades, incluindo personalização de comportamentos de aplicativos por usuário. Cada usuário recebe um armazenamento para as configurações do usuário. Somente os proprietários podem adicionar, modificar e remover configurações do usuário.
  
 **Configurações Globais**
  
As configurações globais são as configurações de usuário pertencentes ao usuário do sistema, e todos os usuários têm acesso somente leitura a eles. As configurações globais são constantes: elas são criadas durante a criação do repositório e nunca mudam.
  
Cada usuário pode substituir as configurações globais criando configurações de usuário com as mesmas chaves. Quando o aplicativo solicita as configurações efetivas do usuário, a API retorna um conjunto de configurações globais mescladas com as configurações do usuário, com cada configuração de usuário sobresondo a respectiva configuração global se as chaves são as mesmas. A API também pode retornar apenas as configurações do usuário para que os aplicativos possam descobrir quais configurações foram substituídos. 
  
As operações REST estão incluídas na tabela a seguir.

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter configurações de usuário](get-user-settings.md) <br/> |Obter configurações de usuário retorna uma lista de configurações para um usuário especificado.  <br/> |
|[Obter configuração de usuário](get-user-setting.md) <br/> |Obter Configuração do Usuário retorna uma configuração de usuário único.  <br/> |
   

