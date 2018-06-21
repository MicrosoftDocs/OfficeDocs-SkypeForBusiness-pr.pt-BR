---
title: Expansor de configurações gerais de aplicativo externo
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Para editar as propriedades de um servidor de aplicativos confiáveis que já foi definido, siga estas instruções.
ms.openlocfilehash: f6acc3f31e294cab08b688327c7cc9b8f25bea3b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19987281"
---
# <a name="external-application-general-settings-expander"></a>Expansor de configurações gerais de aplicativo externo
 
Para editar as propriedades de um servidor de aplicativos confiáveis que já foi definido, siga estas instruções.
  
Há duas seções que você pode modificar:
  
> Configurações gerais
    
> Configurações de próximo salto
    
## <a name="general-settings"></a>Configurações gerais

Você pode modificar o nome de domínio totalmente qualificado (FQDN) atual para o pool de servidores de aplicativos confiáveis. Edite o nome do FQDN do pool. Os registros de host (A) do sistema de nome de domínio (DNS) devem existir para a nova entrada antes de clientes ou servidores podem se conectar para o novo nome do pool.
  
Selecione **habilitar replicação de dados de configuração para este pool** se você precisa ter a replicação de dados de configuração para este pool. Desmarque a marca de seleção se não desejar replicar os dados de configuração.
  
## <a name="next-hop-settings"></a>Configurações de próximo salto

Você pode especificar o servidor de próximo salto do pool de servidores de aplicativos confiáveis, selecionando o pool de Front End do Enterprise Edition ou Standard Edition servidor Front-End de definido na lista suspensa. Um diretor ou diretor pool não é uma seleção válida para um próximo salto do servidor aplicativos confiáveis e não aparecerão na lista.
  
## 

Clique em **Okey** para aceitar e salvar suas alterações. Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.
  

