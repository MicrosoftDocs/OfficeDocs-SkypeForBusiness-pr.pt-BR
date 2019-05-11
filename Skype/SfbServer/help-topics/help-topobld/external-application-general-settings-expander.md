---
title: Expansor de Configurações Gerais de Aplicativo Externo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Para editar as propriedades de um servidor de aplicativos confiáveis que já foi definido, siga estas instruções.
ms.openlocfilehash: fc1a8e567980572e5b58165e156c65ca8030d155
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885543"
---
# <a name="external-application-general-settings-expander"></a>Expansor de Configurações Gerais de Aplicativo Externo
 
Para editar as propriedades de um servidor de aplicativos confiáveis que já foi definido, siga estas instruções.
  
Há duas seções que você pode modificar:
  
> Configurações gerais
> 
> Configurações de próximo salto
    
## <a name="general-settings"></a>Configurações gerais

Você pode modificar o nome de domínio totalmente qualificado (FQDN) atual para o pool de servidores de aplicativos confiáveis. Edite o nome do FQDN do pool. Os registros de host (A) do sistema de nome de domínio (DNS) devem existir para a nova entrada antes de clientes ou servidores podem se conectar para o novo nome do pool.
  
Selecione **habilitar replicação de dados de configuração para este pool** se você precisa ter a replicação de dados de configuração para este pool. Desmarque a marca de seleção se não desejar replicar os dados de configuração.
  
## <a name="next-hop-settings"></a>Configurações de próximo salto

Você pode especificar o servidor de próximo salto do pool de servidores de aplicativos confiáveis, selecionando o pool de Front End do Enterprise Edition ou Standard Edition servidor Front-End de definido na lista suspensa. Um diretor ou diretor pool não é uma seleção válida para um próximo salto do servidor aplicativos confiáveis e não aparecerão na lista.
  


Clique em **Okey** para aceitar e salvar suas alterações. Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.
  

