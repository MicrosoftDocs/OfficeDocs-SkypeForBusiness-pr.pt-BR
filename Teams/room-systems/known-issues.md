---
title: Problemas conhecidos
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: Este artigo aborda os problemas conhecidos das Salas do Microsoft Teams, por área de recurso.
ms.openlocfilehash: fab004336d5a349bd0548479395ef0c25eb642c7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243427"
---
# <a name="known-issues"></a>Problemas conhecidos 
 
Este artigo lista os problemas conhecidos das Salas do Microsoft Teams, por área de recurso.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Atualizar 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
|  Aplicativo desatualizado         |    O console das Salas do Microsoft Teams mostra um erro de "configuração de sistema desatualizada".                |   [Usar a ferramenta de recuperação das Salas do Microsoft Teams](recovery-tool.md)             |  Nenhum |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface do usuário 

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            | --- |
|Teclado virtual ausente   | O teclado virtual não é exibido quando for necessário inserir informações nas Salas do Microsoft Teams. Esse problema ocorre depois de instalar a atualização do Windows 10 para Criadores (versão 1703) no Surface Pro 4 em que esteja executando as Salas do Microsoft Teams. | Para contornar esse problema, abra o teclado virtual manualmente. Para fazer isso, execute estas etapas:<br><br> **1.** Toque e segure na barra de tarefas e, em seguida, toque o botão **Mostrar Teclado Virtual**. Um ícone do teclado deve aparecer no lado direito da barra de tarefas. <br><br> **2.** Toque no ícone do teclado para abrir o teclado virtual. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título do problema |  Comportamento \/ Sintoma | Solução alternativa conhecida | Artigo KB |
|  ---        |      ---             |   ---            |   --- |
| Monitores não detectados | Quando você executa as Salas do Microsoft Teams em um dispositivo Surface Pro (modelo de 2017), monitores não são detectados. |  Mantenha pressionado o botão de energia do Surface Pro por 20 segundos ou mais. Quando você fizer isso, o dispositivo reinicia e limpa o cache de elementos gráficos. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitações e comportamentos esperados

***

O SkypeRoomSystemv2 não oferece suporte à entrada HDCP, pois foi observado que ela causa conflitos com a funcionalidade de ingestão HDMI (vídeo e áudio). Certifique-se que as chaves conectadas às Salas do Microsoft Teams estejam com as opções HDCP desativadas. 

***

Uma TV para consumidor usada como uma exibição de primeira sala deve dar suporte ao recurso de controle de eletrônicos do consumidor (CEC) de HDMI para alternar automaticamente para uma fonte de vídeo ativa a partir do modo de espera. Esse recurso não é suportado em todas as TVs.

***

Use sempre uma conexão de rede de 1-Gbps cabeado para garantir que você tenha a largura de banda necessária. 

***

Se o seu dispositivo de salas do Microsoft Teams perder a confiança com o domínio, você não poderá autenticar no dispositivo e abrir as configurações. Por exemplo, se você remover as salas do Microsoft Teams do domínio após o ingresso no domínio, a confiança será perdida. A solução é fazer logon com a conta de Administrador local. 
***
A versão de 64 bits da edição de aniversário do Windows 10 Enterprise (em inglês, versão 1607) não tem mais suporte em salas do Microsoft Teams da versão 3.0.12.0. 
***
Salas do Microsoft Teams é um aplicativo com várias janelas e requer que a exibição da sala seja conectada à porta HDMI do dispositivo para que o aplicativo funcione corretamente. Verifique se você tem uma tela HDMI conectada ou use um plugue HDMI fictício se estiver testando e ainda não tiver uma exibição adquirida.
***
<a name="See"> </a>  
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
