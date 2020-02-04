---
title: Adicionar Opções de Servidor de Borda para o Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Você define um novo servidor de borda ou um novo pool de bordas e é apresentado à oportunidade de definir recursos para o novo servidor ou pool. As opções que você pode escolher são:'
ms.openlocfilehash: 953aa6c0bcb5d5bf65f0ba649545aef909d3b647
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698356"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Adicionar Opções de Servidor de Borda para o Lync Server 2010

Você define um novo servidor de borda ou um novo pool de bordas e é apresentado à oportunidade de definir recursos para o novo servidor ou pool. As opções que você pode escolher são:

- **Use um único FQDN e endereço IP**: marque a caixa de seleção para usar um único IPv4 ou IPv6 (se optar por usar IPv4 e IPv6, você precisará definir um endereço de cada tipo de endereço IP) e um FQDN (nome de domínio totalmente qualificado) para as interfaces de borda externa.

    > [!IMPORTANT]
    > Se você escolher essa opção, usará apenas um endereço IP ou um IPv4 e um IPv6, mas deverá atribuir números de porta diferentes para cada interface de borda.

- **Habilitar Federação (porta 5061)**: Marque esta caixa de seleção se você fizer a Federação com outras federações, provedores ou ofertas hospedadas do SIP que usam o protocolo de iniciação de sessão (SIP).

- **O endereço IP externo deste pool de bordas é traduzido por Nat**: Marque esta caixa de seleção se você usar endereços IP particulares para as interfaces externas de borda e fornecerá um dispositivo NAT (conversão de endereços de rede) para colocar o servidor de borda ou o pool de bordas logicamente atrás.

## <a name="see-also"></a>Confira também

[Planejando o acesso de usuários externos](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Implantando o acesso de usuários externos](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
