---
title: Expansor de Configurações Gerais de Aplicativo Externo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.
ms.openlocfilehash: 8cdf27598c916f84e96b11d8acfaeb115a0575dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822421"
---
# <a name="external-application-general-settings-expander"></a>Expansor de Configurações Gerais de Aplicativo Externo
 
Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.
  
Existem duas seções que você pode modificar:
  
> Configurações gerais
> 
> Configurações de próximo salto
    
## <a name="general-settings"></a>Configurações Gerais

Você pode modificar o FQDN (nome de domínio totalmente qualificado) para o pool de servidor de aplicativos confiáveis. Edite o nome do pool FQDN. Os registros de host (A) DNS (Domain Name System) devem existir antes que clientes ou servidores possam se conectar ao novo nome de pool.
  
Selecione  **Habilite a replicação dos dados de configuração para este pool** caso você necessite da replicação dos dados de configuração para este pool. Limpe a marca de seleção caso não queira replicar os dados de configuração.
  
## <a name="next-hop-settings"></a>Configurações de Próximo Salto

Você pode especificar o servidor do próximo salto do pool de servidores de aplicativos confiáveis selecionando o pool de Front-End Enterprise Edition definido ou o Servidor de Front End Standard Edition na lista lista drop-down. Um Diretor ou pool de Diretores não é uma escolha válida para um próximo salto de servidor de aplicativos confiáveis e não aparecerão na lista.
  

Clique **em OK** para aceitar e salvar suas alterações. Clique em  **Cancelar** para descartar suas alterações e sair da página de propriedades.
  

