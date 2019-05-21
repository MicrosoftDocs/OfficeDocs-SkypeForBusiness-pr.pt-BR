---
title: Expansor de Configurações Gerais de Aplicativo Externo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.
ms.openlocfilehash: 96118d968a5c9fdf54a78df24019426e562220dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292777"
---
# <a name="external-application-general-settings-expander"></a>Expansor de Configurações Gerais de Aplicativo Externo
 
Para editar as propriedades de um servidor de aplicativos confiável que já foi definido, siga estas instruções.
  
Há duas seções que você pode modificar:
  
> Configurações gerais
> 
> Configurações de próximo salto
    
## <a name="general-settings"></a>Configurações gerais

Você pode modificar o nome de domínio totalmente qualificado (FQDN) atual para o pool do servidor de aplicativos confiável. Edite o nome do FQDN do pool. Os registros de host (A) do sistema de nome de domínio (DNS) devem existir para a nova entrada antes que os clientes ou servidores possam se conectar ao novo nome do pool.
  
Selecione **habilitar a replicação de dados de configuração para esse pool** se você precisar ter a replicação de dados de configuração para esse pool. Desmarque a caixa de seleção se você não quiser replicar os dados de configuração.
  
## <a name="next-hop-settings"></a>Próximas configurações de salto

Você pode especificar o próximo servidor de salto do pool de servidores de aplicativos confiáveis selecionando o pool de front-end do Enterprise Edition definido ou o servidor front-end da edição Standard na lista suspensa. Um diretor ou um pool de diretor não é uma seleção válida para um próximo salto do servidor de aplicativos confiável e não aparecerá na lista.
  

Clique em **OK** para aceitar e salvar as alterações. Clique em **Cancelar** para descartar suas alterações e sair da página de propriedades.
  

