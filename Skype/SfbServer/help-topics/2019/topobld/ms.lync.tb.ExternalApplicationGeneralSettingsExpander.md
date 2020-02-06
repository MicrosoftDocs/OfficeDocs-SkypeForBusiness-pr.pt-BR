---
title: Expansor de Configurações Gerais de Aplicativo Externo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: eacc0c854290fcf24196a8e4c58829231dc725c4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793739"
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
  

