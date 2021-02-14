---
title: 'Suporte à virtualização do Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: saiba mais sobre o suporte à virtualização do Skype for Business Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509028"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Suporte à virtualização do Skype for Business Server 2019

O Skype for Business Server 2019 tem suporte na virtualização.

Embora a virtualização seja suportada, há alguns pontos importantes a lembrar:

- Mantenha uma proporção de 1:1 de CPU virtual para CPU física.
- Não mova um servidor convidado enquanto ele estiver em operação.
- A migração de um sistema ao vivo e a portabilidade de uma máquina virtual não são suportadas.
- Desabilite o hyper-threading em todos os hosts.
- Não configure a memória dinâmica em servidores host.
- Use discos fixos ou de passagem em vez de discos dinâmicos.
- Permitir sobrecarga de 6 a 10% para hipervisores além do que o convidado virtual exige.

## <a name="supported-hypervisors"></a>Hipervisores com suporte

O SfB Server 2019 tem suporte no Windows Server 2016 e no Windows Server 2019.

Para hipervisores de terceiros, você precisa de um hipervisor que passou no teste do Programa de Validação de Virtualização do Servidor (SVVP) para o sistema operacional relevante.

- Consulte as [versões do Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.
- Consulte as [versões do Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.

## <a name="stress-and-performance-tool"></a>Ferramenta de stress and performance

A Ferramenta de Stress and Performance do Skype for Business Server 2019 inclui ferramentas que simplificam o planejamento de capacidade do Skype for Business Server 2019. A Ferramenta de Stress and Performance do Skype for Business Server 2019 ajudará você a:

- Simplificar seu planejamento de hardware para o Skype for Business Server 2019
- Fornecer maior conhecimento e práticas recomendadas para ajuste de desempenho
- Medir o desempenho das implantações pretenddas do Skype for Business Server 2019
 
Você pode baixar a ferramenta [daqui.](https://www.microsoft.com/download/details.aspx?id=101447)
