---
title: Problemas conhecidos
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: O administrador pode aprender sobre uma lista de problemas conhecidos para Salas do Microsoft Teams, incluindo atualização, interface do usuário, hardware e limitações e comportamentos esperados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3656e73226f29f6580a4ae3a1807ee8273731a8
ms.sourcegitcommit: ad215c120d7e550a7aebf2e1bb620c69039e5d8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2021
ms.locfileid: "53679776"
---
# <a name="known-issues"></a>Problemas conhecidos 
 
Este artigo lista os problemas conhecidos das Salas do Microsoft Teams, por área de recurso.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Atualizar 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
| Aplicativo que não está sendo lançado |  Depois de atualizar para o aplicativo versão 4.4.41.0, o sistema será inicializado na tela preta ou vá para a tela de logon após alguns minutos. | Siga as etapas no Salas do Microsoft Teams o aplicativo não inicia após a atualização para a versão [4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) para corrigir esse problema.  | Nenhum |
|  Baixo volume de reunião após o compartilhamento de conteúdo         |   Salas do Microsoft Teams dispositivos no Windows 10 20H2 reduziram a mídia e o volume de reunião após o compartilhamento de conteúdo por meio do HDMI na sala. Isso é causado por um problema de áudio no Windows 10 20H2. | A correção desse problema está disponível no aplicativo versão [4.9.12.0](/microsoftteams/rooms/rooms-release-note#49120-7282021). | Nenhum |
|  Aplicativo desatualizado         |    O console das Salas do Microsoft Teams mostra um erro de "configuração de sistema desatualizada".                |   [Usar a ferramenta de recuperação das Salas do Microsoft Teams](recovery-tool.md)             |  Nenhum |
|  Dispositivo atualizado para versão sem suporte do Windows 10   |    Windows 10 atualizado da versão 1803 para a versão 1809, que não é suportado. A versão com suporte é 1903. |   Isso pode acontecer se a configuração de Política de Grupo ou [MDM para DeferFeatureUpdatesPeriodinDays,](/windows/deployment/update/waas-configure-wufb) que permite adiar as atualizações de recursos para um número especificado de dias, estiver definida como o máximo de 365 dias. <br><br> Windows 10 versão 1809 não é suportada com Salas do Microsoft Teams, enquanto a versão 1903 é suportada. No entanto, a partir de 27 de março de 2020, a versão 1809 tem mais de 365 dias. Se essa configuração não for alterada, Windows tentar instalar a versão 1809, o que pode causar problemas com Salas do Microsoft Teams.<br><br>Para evitar essa situação, **remova qualquer** configuração de Política de Grupo ou MDM para adiar atualizações. Isso permite Windows atualizar para a versão mais recente e suportada do sistema operacional. <br><br>**IMPORTANTE** A configuração de Política de Grupo ou MDM deve ser **removida** (não configurada à esquerda) e não **definida como 0**. Se a política for definida como 0, Windows a versão mais recente disponível que pode não ter suporte. |  Nenhum |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface do usuário 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
|Teclado virtual ausente   | O teclado virtual não é exibido quando for necessário inserir informações nas Salas do Microsoft Teams. Esse problema ocorre no Windows 10, versão 1903. | Instale a Atualização Cumulativa 2020-04 para Windows 10, versão 1903 para sistemas baseados em x64 por meio de Windows Atualizações.  | Nenhum | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            |   --- |
| Monitores não detectados | Quando você executa as Salas do Microsoft Teams em um dispositivo Surface Pro (modelo de 2017), monitores não são detectados. |  Mantenha pressionado o botão de energia do Surface Pro por 20 segundos ou mais. Quando você fizer isso, o dispositivo reinicia e limpa o cache de elementos gráficos. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitações e comportamentos esperados

***

O SkypeRoomSystemv2 não oferece suporte à entrada HDCP, pois foi observado que ela causa conflitos com a funcionalidade de ingestão HDMI (vídeo e áudio). Certifique-se que as chaves conectadas às Salas do Microsoft Teams estejam com as opções HDCP desativadas. 

***

Se você desejar que uma tela frontal da sala alterna automaticamente para uma fonte de vídeo ativa (como um console MTR) quando a origem acordar do modo de espera, determinadas condições devem ser atendidas. Esse recurso é opcional, mas tem suporte Salas do Microsoft Teams software, desde que o hardware subjacente suporte o recurso. Uma TV de consumidor usada como tela frontal de sala precisa dar suporte ao recurso CeC (Controle eletrônico de consumidor) do HDMI.  Dependendo do dock ou console selecionado (que pode não dar suporte ao CEC, consulte a documentação de suporte do fabricante), um controlador como [um HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron pode ser necessário para habilitar o comportamento desejado. 

***

Sempre use uma conexão de rede com 1 Gbps com fio para garantir que você tenha a largura de banda necessária. 

***

Se o dispositivo Salas do Microsoft Teams perde a confiança com o domínio, você não poderá se autenticar no dispositivo e abrir Configurações. Por exemplo, se você remover o Salas do Microsoft Teams do domínio depois que ele for ingressado no domínio, a confiança será perdida. A solução é fazer logon com a conta de Administrador local. 
***
Salas do Microsoft Teams é um aplicativo de várias janelas e exige que uma tela frontal da sala seja conectada à porta HDMI do dispositivo, para que o aplicativo funcione corretamente. Certifique-se de que você tenha uma exibição HDMI conectada ou use um plug HDMI fictício se você estiver testando e ainda não tiver uma exibição comprada.
***
<a name="See"> </a>  
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
