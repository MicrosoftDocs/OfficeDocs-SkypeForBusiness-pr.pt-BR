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
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Você define um novo servidor de borda ou um pool de borda e é apresentado à oportunidade de definir recursos para o novo servidor ou pool. As opções possíveis são:'
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216592"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Adicionar Opções de Servidor de Borda para o Lync Server 2010

Você define um novo servidor de borda ou um pool de borda e é apresentado à oportunidade de definir recursos para o novo servidor ou pool. As opções possíveis são:

- **Usar um único FQDN e endereço IP**: marque a caixa de seleção para usar um único endereço IPv4 ou IPv6 (se você escolher usar IPv4 e IPv6, será necessário definir um de cada tipo de endereço IP) e nome de domínio totalmente qualificado (FQDN) para as interfaces de Borda externas.

    > [!IMPORTANT]
    > Se você escolher essa opção, usará somente um endereço IP ou um IPv4 e um IPv6, mas deverá atribuir números de porta diferentes a cada interface de Borda.

- **Habilitar federação (porta 5061)**: marque essa caixa de seleção se for federar com outras federações SIP, provedores ou ofertas hospedadas que usam o protocolo de início de sessão (SIP).

- **O endereço IP externo deste pool de borda é convertido pelo NAT**: Marque essa caixa de seleção se você usar endereços IP privados para as interfaces externas de borda e fornecerá um dispositivo NAT (conversão de endereço de rede) para colocar o servidor de borda ou o pool de borda logicamente atrás.

## <a name="see-also"></a>Confira também

[Planejando o acesso de usuários externos](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Implantação de acesso de usuários externos](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
