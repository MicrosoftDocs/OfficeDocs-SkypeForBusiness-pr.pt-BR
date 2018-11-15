---
title: Serviço de configurações de usuário para o painel de controle de qualidade de chamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Resumo: Saiba mais sobre o serviço de configurações de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 00d0662e777ef2f13c9783fe4b79d5c582faa8af
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531888"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Serviço de configurações de usuário para o painel de controle de qualidade de chamada (CQD)
 
**Resumo:** Saiba mais sobre o serviço de configurações de usuário, que é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.
  
O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada.
  
## <a name="user-settings-service"></a>Serviço de configurações de usuário

Configurações do usuário são pares de chave-valor que os aplicativos podem usar para armazenar metadados para várias finalidades, incluindo a personalização da base do aplicativo comportamentos por usuário. Cada usuário recebe um armazenamento de configurações do usuário. Somente os proprietários podem adicionar, modificar e remover as configurações do usuário.
  
 **Configurações globais**
  
Configurações globais são as configurações de usuário pertencentes ao usuário do sistema e todos os usuários têm acesso somente leitura a eles. Configurações globais são constantes: forem criados durante a criação do repositório, e elas nunca alteram.
  
Cada usuário pode substituir as configurações globais através da criação de configurações de usuário com as mesmas chaves. Quando o aplicativo solicita as configurações de usuário efetivo, a API retorna um conjunto de configurações globais mescladas com as configurações de usuário, com cada configuração de usuário seja substituído a respectiva configuração global se chaves são iguais. A API também pode retornar apenas as configurações do usuário para que os aplicativos podem descobrir quais configurações são substituídas. 
  
As operações do REST estão incluídas na tabela a seguir.

|**Operação**|**Descrição**|
|:-----|:-----|
|[Obter configurações de usuário](get-user-settings.md) <br/> |Configurações de usuário Get retorna uma lista de configurações para um usuário especificado.  <br/> |
|[Obter a configuração do usuário](get-user-setting.md) <br/> |Obtenha a configuração do usuário retorna a configuração de um único usuário.  <br/> |
   

