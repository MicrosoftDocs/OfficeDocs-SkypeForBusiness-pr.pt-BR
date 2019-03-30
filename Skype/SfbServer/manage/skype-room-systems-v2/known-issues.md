---
title: Problemas conhecidos
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: Este artigo discute problemas conhecidos para salas de equipes da Microsoft, pela área de recurso.
ms.openlocfilehash: d71b209784f4737ac4433e2eececb1f9ada3ebc8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013084"
---
# <a name="known-issues"></a>Problemas conhecidos 
 
Este artigo lista os problemas conhecidos para salas de equipes da Microsoft, pela área de recurso.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Atualização 

| Título do problema |  Comportamento \/ sintoma | Solução alternativa conhecida | Artigo da KB |
|  ---        |      ---             |   ---            | --- |
|  App desatualizada         |    O console de salas de equipes da Microsoft mostra um erro "system config desatualizada".                |   [Use a ferramenta de recuperação de salas de equipes da Microsoft](recovery-tool.md)             |  Nenhum |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface do usuário 

| Título do problema |  Comportamento \/ sintoma | Solução alternativa conhecida | Artigo da KB |
|  ---        |      ---             |   ---            | --- |
|Teclado virtual ausentes   | O teclado virtual não aparece quando você precisa inserir informações em salas de equipes da Microsoft. Esse problema ocorre após a atualização de criadores de 10 do Windows (versão 1703) está instalada no 4 Surface Pro onde salas de equipes da Microsoft está sendo executado. | Para contornar esse problema, abra o teclado virtual manualmente. Para fazer isso, siga estas etapas:<br><br> **1.** toque e mantenha a barra de tarefas e, em seguida, toque em botão **teclado de toque de Mostrar** . Um ícone de teclado deve aparecer no lado direito da barra de tarefas. <br><br> **2.** toque no ícone de teclado para abrir o teclado virtual. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título do problema |  Comportamento \/ sintoma | Solução alternativa conhecida | Artigo da KB |
|  ---        |      ---             |   ---            |   --- |
| Monitores não detectados | Quando você executa o Microsoft equipes salas em um dispositivo Surface Pro (modelo de 2017), monitores não são detectados. |  Mantenha pressionado o botão de alimentação de Surface Pro por 20 ou mais segundos. Quando você fizer isso, o dispositivo é reiniciado e limpa o cache de elementos gráficos. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Comportamentos esperados e limitações
***
Salas de equipes da Microsoft não oferece suporte a entrada HDCP, o que foi observada causar problemas com HDMI absorver funcionalidade (vídeo, áudio). Tome cuidado para garantir que os switches conectados ao Microsoft equipes salas tenham opções HDCP desativadas. 
***
A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs. 
***
Sempre use uma conexão de rede 1 Gbps com fio para garantir que você terá a largura de banda necessária. 
***
Se o seu dispositivo Microsoft equipes salas perde a confiança com o domínio (por exemplo, se você remover as salas de equipes da Microsoft do domínio depois que ele for unido ao domínio), você não conseguirá autenticar no dispositivo e abra o backup das configurações. Como alternativa, é possível entrar com a conta de Administrador local. 
***
A versão de 64 bits do Windows 10 aniversário no Enterprise edition (idioma inglês, versão 1607) não é mais suportado a partir do Microsoft equipes salas release 3.0.12.0. 
***

<a name="See"> </a>  
## <a name="see-also"></a>Consulte Também

[Ajuda do Microsoft equipes salas](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar salas de equipes da Microsoft](skype-room-systems-v2.md)