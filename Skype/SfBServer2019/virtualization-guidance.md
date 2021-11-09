---
title: 'Suporte a virtualização para Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Resumo: saiba mais sobre o suporte à virtualização para Skype for Business Server 2019.'
ms.openlocfilehash: 73e9121e2b530e44395aefda50082682fb910e7d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853775"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Suporte a virtualização para Skype for Business Server 2019

Skype for Business Server 2019 é suportado na virtualização.

Embora a virtualização seja suportada, há alguns pontos-chave a lembrar:

- Mantenha uma taxa de 1:1 da CPU virtual para a CPU física.
- Não mova um servidor convidado enquanto ele estiver operando.
- Não há suporte para a migração de um sistema ao vivo e a portabilidade de uma máquina virtual.
- Desabilite o hiper threading em todos os hosts.
- Não configure a memória dinâmica em servidores host.
- Use discos fixos ou de passagem em vez de discos dinâmicos.
- Permitir uma sobrecarga de 6 a 10% para hipervisores além do que o convidado virtual exige.

## <a name="supported-hypervisors"></a>Hipervisores com suporte

O SfB Server 2019 tem suporte no Windows Server 2016 e Windows Server 2019.

Para hipervisores de terceiros, você precisa de um hipervisor que tenha passado no teste do Programa de Validação de Virtualização do Servidor (SVVP) para o sistema operacional relevante.

- Consulte as [Windows Server 2016 na](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) lista SVVP.
- Consulte as [Windows versões do Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.

## <a name="stress-and-performance-tool"></a>Ferramenta de estresse e desempenho

A Skype for Business Server ferramenta de desempenho e estresse 2019 inclui ferramentas que simplificam o planejamento de capacidade para Skype for Business Server 2019. A Skype for Business Server ferramenta de desempenho e estresse do 2019 ajudará você a:

- Simplificar seu planejamento de hardware para Skype for Business Server 2019
- Fornecer maior conhecimento e práticas recomendadas para ajuste de desempenho
- Medir o desempenho de suas implantações Skype for Business Server 2019 pretendido
 
Você pode baixar a ferramenta [daqui](https://www.microsoft.com/download/details.aspx?id=101447).
