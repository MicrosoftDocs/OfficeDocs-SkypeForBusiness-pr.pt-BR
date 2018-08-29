---
title: Expansor de configurações de Site do Lync Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar as propriedades de um site existente, faça o seguinte:'
ms.openlocfilehash: b9660fcfbabc1276a5a470d6f83752981c35c54f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258232"
---
# <a name="lync-server-site-settings-expander"></a>Expansor de configurações de Site do Lync Server

Para editar as propriedades de um site existente, faça o seguinte:



## <a name="site-properties"></a>Propriedades do site

Nas propriedades do site, você pode alterar ou modificar o nome (obrigatório) do site, descrição (opcional), cidade (opcional), estado/província (opcional) e o código de país/região (opcional).

Para obter detalhes sobre propriedades do site, consulte [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Propriedades de rota de Federação

Para definir uma atribuição de rota de Federação do site, você primeiro deve ter a federação habilitada em um servidor de borda ou um pool do servidor de borda. Se a federação não está habilitada em um servidor de borda ou pool, as configurações de atribuição de rota de federação para o site não estará disponíveis para modificação.

Se a configuração de federação no servidor de borda ou pool tiver sido configurada, selecione **Habilitar** no nível do site. Selecione uma borda ou um diretor na lista suspensa para definir como a rota de Federação.

> [!CAUTION]
> Essa configuração afetará todos os sites. Certifique-se de que a configuração que você está configurando neste site é apropriada para todos os sites.

## <a name="see-also"></a>Consulte também

Para obter detalhes, consulte [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


