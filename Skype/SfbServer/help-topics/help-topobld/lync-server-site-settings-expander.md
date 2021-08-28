---
title: Expansor de Configurações de Site do Servidor Lync
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Para editar as propriedades de um local existente, faça o seguinte:'
ms.openlocfilehash: 09aa876d8f1624b626325c625b820ddb1f6b7aa5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591335"
---
# <a name="lync-server-site-settings-expander"></a>Expansor de Configurações de Site do Servidor Lync

Para editar as propriedades de um local existente, faça o seguinte:



## <a name="site-properties"></a>Propriedades do Site

Nas propriedades do site você pode alterar ou modificar o Nome (exigido) do site, a Descrição (opcional), Cidade (opcional), Estado/Província (opcional) e o Código de País/Região (opcional).

Para maiores detalhes sobre propriedades do site, consulte  [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).

## <a name="federation-route-properties"></a>Propriedades de Rota de Federação

Para definir uma atribuição de rota de federação, você deve primeiro ter a federação ativada em um Servidor de Borda ou um pool de Servidor de Borda. Caso a federação não esteja ativada em um pool ou Servidor de Borda, as configurações de atribuição de rota de federação para o site não estarão disponíveis para alterações.

Caso a configuração de federação no pool ou Servidor de Borda tenha sido configurada, selecione **Ativar** no nível do site. Em seguida, selecione uma Borda ou Diretor a partir da lista suspensa para definir como rota de federação.

> [!CAUTION]
> Essa definição afetará todos os sites. Assegure-se de que a definição que você está configurando neste site é apropriada para todos os sites.

## <a name="see-also"></a>Confira também

Para obter detalhes, consulte  [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).