---
title: Suporte de versão
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo discute o suporte do ciclo de vida para salas do Microsoft Teams.
ms.openlocfilehash: e5142d23d9f57a6ca50bcdb348378084afffd86b
ms.sourcegitcommit: 1bb3df681177db5ecc6afae3d3f3a46c251e5c23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43117519"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Suporte à versão do aplicativo salas do Microsoft Teams
 
O aplicativo salas do Microsoft Teams é atualizado há algumas vezes por ano. Cada atualização aceita por doze (12) meses a partir da data de lançamento do GA (disponibilidade geral). O suporte técnico é oferecido para os doze (12) meses inteiros. No entanto, a estrutura de suporte é dinâmica, com duas fases distintas que dependem da disponibilidade da versão mais recente:

- \- **Fase de manutenção e atualizações críticas** ao executar a versão mais recente do aplicativo salas do Microsoft Teams, você recebe atualizações regulares que contêm atualizações *de segurança e manutenção* .

- **Atualizações de segurança somente fase** \- quando uma nova versão do aplicativo salas do Microsoft Teams é liberada, as versões mais antigas do aplicativo têm um nível de suporte reduzido com *atualizações de segurança somente* para o restante do ciclo de vida de doze (12) meses.

> [!NOTE]
> A versão mais recente está sempre na fase manutenção e atualizações críticas. Quando você encontra um defeito de código que garante uma atualização crítica, você também deve ter a versão mais recente instalada para receber uma correção. Todas as outras versões com suporte só serão elegíveis para receber atualizações de segurança.

O suporte será encerrado depois que o ciclo de vida de doze (12) meses tiver expirado ou se mais de duas atualizações tiverem sido lançadas desde então. Em seguida, os clientes devem atualizar para uma versão com suporte.

Todas as versões estão listadas nas [notas de versão das salas do Microsoft Teams](rooms-release-note.md).

## <a name="windows-10-release-support"></a>Suporte para versões do Windows 10

As salas do Microsoft Teams exigem as SKUs Windows 10 IoT Enterprise ou Windows 10 Enterprise em opções de serviços de canal semestral. Não há suporte para essas outras edições do Windows 10:

- As edições do Windows 10 Enterprise (corporativo)/canal de serviço de longo prazo (LTSC)
- Edições do Windows 10 corporativo/LTSC do Windows 10 para empresas
- qualquer outra edição do Windows, como o Windows 10 pro ou Home Edition

Uma atualização de recursos do Windows 10 não é oferecida ou atualizada imediatamente nos dispositivos de salas do Microsoft Teams. Um atraso intencional de até seis meses após a data de disponibilidade geral publicada na página [informações de lançamento do Windows 10](https://docs.microsoft.com/windows/release-information/) . O tempo de atraso é usado para validar a compatibilidade de versão do Windows 10 para o aplicativo de salas do Microsoft Teams, hardware de dispositivo e periféricos de vídeo de áudio certificados. A validação começa e continua durante o desenvolvimento ativo de cada lançamento principal do Windows 10. É preciso mais tempo para validar que todos os fabricantes de dispositivos criaram imagens atualizadas para seus dispositivos e o Microsoft Teams para certificar e testar essas imagens. Durante o período de validação, o aplicativo da sala Microsoft Teams usa [as políticas de grupo do Windows Update para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para atrasar atualizações de recursos do Windows 10. Após qualquer problema de compatibilidade ser encontrado e resolvido, o bloco é levantado por meio da atualização das políticas de grupo por meio de uma nova versão do aplicativo na Windows Store. Dispositivos que executam o aplicativo salas do Microsoft Teams são atualizados automaticamente para uma versão apropriada do Windows 10 durante a reinicialização noturna da manutenção. Uma versão MSI é disponibilizada para os clientes que desejam gerenciar manualmente as atualizações.  

> [!IMPORTANT]
> Durante o período de validação, os dispositivos de salas do Microsoft Teams **não** devem ser atualizados para o próximo lançamento do Windows 10 por meio de qualquer meio. Isso inclui substituir as políticas de grupo no lugar ou usar o System Center ou outros serviços de gerenciamento de dispositivos de terceiros. Qualquer um desses pode causar problemas para o aplicativo da sala Microsoft Teams ou deixar dispositivos inutilizáveis.  

A tabela a seguir mostra as versões recomendadas e com suporte do Windows 10 que são verificadas para dar suporte a salas do Microsoft Teams. Todas as datas são listadas no formato ISO 8601: YYYY-MM-DD.

|Versão  |Data de disponibilidade   |Status de suporte de salas do Microsoft Teams   |Sala mínima de salas do Microsoft Teams versão do aplicativo | Build do sistema operacional recomendado  |
|:---  |:---       |:---                                  |:---     |:---     |
| 1909 |2019-11-12 |Validando no momento, <br/>Não recomendado|&#x2014; |&#x2014; |
| 1903 |2019-05-21 |Suporte <br/>Recomendado  |4.2.4.0 |18362,356 |
| 1809 |2019-03-28 |Ignorada <br/>Não recomendado &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Com suporte                             |4.1.22.0 |17134,191|
| 1709 |2018-01-18 |Incompatível                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Sem suporte                         |&#x2014; |&#x2014; |

&#x2781; a versão do Windows 10 1809 não é recomendada devido a problemas de compatibilidade encontrados com o aplicativo salas do Microsoft Teams. Esse problema específico faz com que o aplicativo salas do Microsoft Teams falhe ao iniciar após a reinicialização noturna. Esse problema foi resolvido na versão do Windows 10 1903.  

Ao usar uma versão com suporte do Windows 10, você sempre terá as atualizações mais recentes do aplicativo para o aplicativo salas do Microsoft Teams.  

## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salas de lançamento das salas do Microsoft Teams](rooms-release-note.md)

[Plano para salas do Microsoft Teams](rooms-plan.md)
