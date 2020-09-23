---
title: Expansor de Configurações de Site do Servidor Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Para editar as propriedades de um local existente, faça o seguinte:'
ms.openlocfilehash: 69555a04be4125e213ba2eca7afd7255100c0444
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217562"
---
# <a name="lync-server-site-settings-expander"></a>Expansor de Configurações de Site do Servidor Lync

Para editar as propriedades de um local existente, faça o seguinte:



## <a name="site-properties"></a>Propriedades do Site

Nas propriedades do site você pode alterar ou modificar o Nome (exigido) do site, a Descrição (opcional), Cidade (opcional), Estado/Província (opcional) e o Código de País/Região (opcional).

Para maiores detalhes sobre propriedades do site, consulte  [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Propriedades de Rota de Federação

Para definir uma atribuição de rota de federação, você deve primeiro ter a federação ativada em um Servidor de Borda ou um pool de Servidor de Borda. Caso a federação não esteja ativada em um pool ou Servidor de Borda, as configurações de atribuição de rota de federação para o site não estarão disponíveis para alterações.

Caso a configuração de federação no pool ou Servidor de Borda tenha sido configurada, selecione **Ativar ** no nível do site. Em seguida, selecione uma Borda ou Diretor a partir da lista suspensa para definir como rota de federação.

> [!CAUTION]
> Essa definição afetará todos os sites. Assegure-se de que a definição que você está configurando neste site é apropriada para todos os sites.

## <a name="see-also"></a>Confira também

Para obter detalhes, consulte  [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


