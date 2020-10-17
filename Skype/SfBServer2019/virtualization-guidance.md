---
title: 'Suporte de virtualização para o Skype for Business Server 2019 '
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
description: 'Resumo: Saiba mais sobre o suporte de virtualização para o Skype for Business Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509028"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Suporte de virtualização para o Skype for Business Server 2019

O Skype for Business Server 2019 é suportado na virtualização.

Embora haja suporte à virtualização, há alguns pontos importantes a serem lembrados:

- Mantenha uma taxa de 1:1 de CPU virtual para a CPU física.
- Não mova um servidor convidado enquanto ele está funcionando.
- Não há suporte para a migração de um sistema ativo e portabilidade de uma máquina virtual.
- Desabilite o Hyper-Threading em todos os hosts.
- Não configure a memória dinâmica nos servidores host.
- Usar discos fixos ou de passagem em vez de discos dinâmicos.
- Permitir a sobrecarga de 6-10% para os hipervisores além do que o convidado virtual exige.

## <a name="supported-hypervisors"></a>Hipervisores suportados

O SfB Server 2019 é suportado no Windows Server 2016 e no Windows Server 2019.

Para hipervisores de terceiros, você precisa de um hipervisor que passou no teste SVVP (Server Virtualization Validation Program) para o sistema operacional relevante.

- Consulte as [versões do Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.
- Consulte as [versões do Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) na lista SVVP.

## <a name="stress-and-performance-tool"></a>Ferramenta de estresse e desempenho

A ferramenta de estresse e desempenho do Skype for Business Server 2019 inclui ferramentas que simplificam o planejamento de capacidade para o Skype for Business Server 2019. A ferramenta de desempenho e stress do Skype for Business Server 2019 ajudará você a:

- Simplificar o planejamento de hardware para o Skype for Business Server 2019
- Fornecer mais conhecimento e práticas recomendadas para ajuste de desempenho
- Meça o desempenho de suas implantações pretendidas do Skype for Business Server 2019
 
Você pode baixar a ferramenta [aqui](https://www.microsoft.com/download/details.aspx?id=101447).
