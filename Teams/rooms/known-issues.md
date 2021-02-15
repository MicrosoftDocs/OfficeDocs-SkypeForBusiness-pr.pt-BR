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
description: O administrador pode saber mais sobre uma lista de problemas conhecidos das Salas do Microsoft Teams, incluindo atualização, interface do usuário, hardware e limitações e comportamentos esperados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63a646fa6fb404cb46de889c318181146cb44b2a
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055733"
---
# <a name="known-issues"></a>Problemas conhecidos 
 
Este artigo lista os problemas conhecidos das Salas do Microsoft Teams, por área de recurso.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Atualizar 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
| Aplicativo não iniciando |  Depois de atualizar para a versão 4.4.41.0 do aplicativo, o sistema será inicializado na tela preta ou vá para a tela de logon após alguns minutos. | Siga as etapas no aplicativo Salas do Microsoft Teams não começa após a atualização para a versão [4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) para corrigir esse problema.  | Nenhum |
|  O compartilhamento de conteúdo de reuniões SfB não é exibido em tela inteira         |    Em reuniões do Skype for Business, salas com exibições de frente para sala usando configurações de DPI alto podem ter problemas em que o conteúdo compartilhado em uma reunião não mostra a tela inteira na frente da exibição da sala. Isso é causado por um problema subjacente na API RDP (Remote Desktop Protocol) do Windows 10. | Use a `<WinRTRdpEnabled>` configuração XML para desabilitar a API RDP do Windows 10 para resolver esse problema. Para desabilitar, você precisa especificar o valor como `false` . Para obter mais informações, consulte [Gerenciar configurações do console com um arquivo de configuração XML.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | Nenhum |
|  Aplicativo desatualizado         |    O console das Salas do Microsoft Teams mostra um erro de "configuração de sistema desatualizada".                |   [Usar a ferramenta de recuperação das Salas do Microsoft Teams](recovery-tool.md)             |  Nenhum |
|  Dispositivo atualizado para a versão sem suporte do Windows 10   |    Dispositivo Windows 10 atualizado da versão 1803 para a versão 1809, que não tem suporte. A versão com suporte é 1903. |   Isso pode acontecer se a configuração de Política de Grupo ou MDM para a configuração [DeferFeatureUpdatesPeriodinDays,](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) que permite adiar atualizações de recursos para um número especificado de dias, estiver definida para o máximo de 365 dias. <br><br> O Windows 10 versão 1809 não tem suporte no Microsoft Teams Rooms, enquanto a versão 1903 tem suporte. No entanto, a partir de 27 de março de 2020, a versão 1809 tem mais de 365 dias. Se essa configuração não for alterada, o Windows tentará instalar a versão 1809, o que pode causar problemas com as Salas do Microsoft Teams.<br><br>Para evitar essa situação, **remova qualquer** configuração de Política de Grupo ou MDM para adiar atualizações. Isso permite que o Windows atualize para a versão mais recente do sistema operacional com suporte. <br><br>**IMPORTANTE** A configuração de Política de Grupo ou MDM deve ser removida **(não** configurada à esquerda) e não **definida como 0.** Se a política estiver definida como 0, o Windows ficará com a versão disponível mais recente, que pode não ser suportada. |  Nenhum |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface do usuário 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
|Teclado virtual ausente   | O teclado virtual não é exibido quando for necessário inserir informações nas Salas do Microsoft Teams. Esse problema ocorre no Windows 10, versão 1903. | Instale a Atualização Cumulativa 2020-04 para Windows 10, versão 1903 para sistemas baseados em x64 por meio das Atualizações do Windows.  | Nenhum | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            |   --- |
| Monitores não detectados | Quando você executa as Salas do Microsoft Teams em um dispositivo Surface Pro (modelo de 2017), monitores não são detectados. |  Mantenha pressionado o botão de energia do Surface Pro por 20 segundos ou mais. Quando você fizer isso, o dispositivo reinicia e limpa o cache de elementos gráficos. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitações e comportamentos esperados

**_

O SkypeRoomSystemv2 não oferece suporte à entrada HDCP, pois foi observado que ela causa conflitos com a funcionalidade de ingestão HDMI (vídeo e áudio). Certifique-se que as chaves conectadas às Salas do Microsoft Teams estejam com as opções HDCP desativadas. 

_*_

Se você desejar que uma exibição na frente da sala alternar automaticamente para uma fonte de vídeo ativa (como um console MTR) quando a fonte desperta do modo de espera, certas condições devem ser atendidas. Esse recurso é opcional, mas compatível com o software Salas do Microsoft Teams, fornecido com suporte para o recurso de hardware subjacente. Uma TV de consumidor usada como uma frente de exibição de sala precisa dar suporte ao recurso CONTROLE de Eletrônica do Consumidor (CEC) de HDMI.  Dependendo do encaixe ou do console selecionado (que pode não dar suporte ao CEC, consulte a documentação de suporte do fabricante), um controlador como [um HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) doTexron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron pode ser necessário para habilitar o comportamento desejado. 

_*_

Sempre use uma conexão de rede com 1 Gbps para garantir que você tem a largura de banda necessária. 

_*_

Se seu dispositivo Salas do Microsoft Teams perder a confiança com o domínio, você não poderá se autenticar no dispositivo e abrir Configurações. Por exemplo, se você remover as Salas do Microsoft Teams do domínio depois que o domínio for ingressado, a confiança será perdida. A solução é fazer logon com a conta de Administrador local. 
_*_ O Microsoft Teams Rooms é um aplicativo de várias janelas e requer que uma tela frontal da sala seja conectada à porta HDMI do dispositivo para que o aplicativo funcione corretamente. Certifique-se de que você tenha um monitor HDMI conectado ou use um conector HDMI simulado se estiver testando e ainda não tiver comprado um vídeo.
_** <a name="See"> </a>  
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
