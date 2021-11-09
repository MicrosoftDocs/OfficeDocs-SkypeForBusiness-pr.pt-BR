---
title: Expansor de Configurações Gerais de Aplicativo Externo
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.
ms.openlocfilehash: 1941b32b24138ba87877f0bb262928e1d0b972dc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843174"
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

Você pode especificar o servidor de próximo salto do pool de servidores de aplicativos confiável selecionando o pool de front-end definido Edição Enterprise ou Edição Standard Servidor Front-End na listada. Um Diretor ou pool de Diretores não é uma escolha válida para um próximo salto de servidor de aplicativos confiáveis e não aparecerão na lista.
  

Clique **em OK** para aceitar e salvar suas alterações. Clique em  **Cancelar** para descartar suas alterações e sair da página de propriedades.
  

