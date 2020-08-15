---
title: Problemas conhecidos
ms.author: v-lanac
author: lanachin
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
description: O administrador pode saber mais sobre uma lista de problemas conhecidos para salas do Microsoft Teams, incluindo atualização, interface do usuário, hardware e limitações e comportamentos esperados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 584b71d39552990b3e4009efb177ef4fee61f1a4
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761337"
---
# <a name="known-issues"></a>Problemas conhecidos 
 
Este artigo lista os problemas conhecidos das Salas do Microsoft Teams, por área de recurso.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Atualizar 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
| Aplicativo não inicializado |  Após a atualização para a versão do aplicativo 4.4.41.0, o sistema é inicializado para tela preta ou acesse a tela de logon após alguns minutos. | Siga as etapas no [aplicativo salas do Microsoft Teams não inicia após a atualização para a versão 4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) para corrigir esse problema.  | Nenhum |
|  O compartilhamento de conteúdo de reuniões do SfB não mostra a tela inteira         |    Nas reuniões do Skype for Business, as salas com a frente da sala exibem as configurações de DPI alto podem apresentar problemas em que o conteúdo compartilhado em uma reunião não mostra a tela inteira na frente da exibição da sala. Isso é causado por um problema subjacente na API do protocolo RDP (protocolo de área de trabalho remota) do Windows 10. | Use a `<WinRTRdpEnabled>` configuração XML para desabilitar a API do Windows 10 RDP para resolver esse problema. Para desabilitar, você precisa especificar o valor como `false` . Para obter mais informações, consulte [Gerenciando configurações de console com um arquivo de configuração XML](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file). | Nenhum |
|  Aplicativo desatualizado         |    O console das Salas do Microsoft Teams mostra um erro de "configuração de sistema desatualizada".                |   [Usar a ferramenta de recuperação das Salas do Microsoft Teams](recovery-tool.md)             |  Nenhum |
|  Dispositivo atualizado para uma versão sem suporte do Windows 10   |    Dispositivo Windows 10 atualizado da versão 1803 para a versão 1809, que não tem suporte. A versão compatível é 1903. |   Isso pode acontecer se a configuração de [política de grupo ou de MDM para DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) , que permite adiar atualizações de recursos para um número específico de dias, é definida como o máximo de 365 dias. <br><br> O Windows 10 versão 1809 não é compatível com as salas do Microsoft Teams, enquanto a versão 1903 tem suporte. No entanto, a partir de 27 de março de 2020, a versão 1809 tem mais de 365 dias de idade. Se essa configuração não for alterada, o Windows tenta instalar a versão 1809, que pode causar problemas com as salas do Microsoft Teams.<br><br>Para evitar essa situação, **remova** todas as configurações de política de grupo ou MDM para adiar atualizações. Isso permite que o Windows atualize para a versão do sistema operacional compatível mais recente. <br><br>**Importante** A política de grupo ou a configuração do MDM deve ser **removida** (esquerda não configurada) e **não definida como 0**. Se a política estiver definida como 0, o Windows usará a versão mais recente disponível, que pode não ser suportada. |  Nenhum |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface do usuário 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
|Teclado virtual ausente   | O teclado virtual não é exibido quando for necessário inserir informações nas Salas do Microsoft Teams. Esse problema ocorre no Windows 10, versão 1903. | Instale a atualização cumulativa do 2020-04 para Windows 10, versão 1903 para sistemas baseados em x64 por meio das atualizações do Windows.  | Nenhum | 

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

Se você quiser uma exibição do lado da sala para alternar automaticamente para uma fonte de vídeo ativa (como um console do MTR) quando a origem é ativada do modo de espera, determinadas condições devem ser atendidas. Esse recurso é opcional, mas suportado pelo software de salas Microsoft Teams, desde que o hardware subjacente seja compatível com o recurso. Uma TV para consumidor usada como uma frontal da exibição de sala precisa dar suporte ao recurso de controle de eletrônicos do consumidor (CEC) de HDMI.  Dependendo do Dock ou console selecionado (que pode não ser compatível com o CEC, confira a documentação de suporte do fabricante), um controlador de espaço de trabalho como um [EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad) pode ser necessário para habilitar o comportamento desejado. 

***

Use sempre uma conexão de rede de 1-Gbps cabeado para garantir que você tenha a largura de banda necessária. 

***

Se o seu dispositivo de salas do Microsoft Teams perder a confiança com o domínio, você não poderá autenticar no dispositivo e abrir as configurações. Por exemplo, se você remover as salas do Microsoft Teams do domínio após o ingresso no domínio, a confiança será perdida. A solução é fazer logon com a conta de Administrador local. 
***
Salas do Microsoft Teams é um aplicativo com várias janelas e requer que a exibição da sala seja conectada à porta HDMI do dispositivo para que o aplicativo funcione corretamente. Verifique se você tem uma tela HDMI conectada ou use um plugue HDMI fictício se estiver testando e ainda não tiver uma exibição adquirida.
***
<a name="See"> </a>  
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
