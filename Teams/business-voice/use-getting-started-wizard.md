---
title: Usar o assistente do Guia de Introdução para configurar o Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e6ed778af0136516286798b0a7b04602f571de2
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653527"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>Usar o assistente do Guia de Introdução para configurar o Business Voice

O assistente do Guia de Introdução do Microsoft 365 Business Voice oferece uma maneira fácil e rápida de começar a fazer e receber chamadas telefônicas no Microsoft Teams. Se você estiver começando a trabalhar em uma empresa pequena, o assistente consegue colocá-lo para trabalhar em alguns minutos com números de telefone, menus de chamadas, saudações e muito mais. Se você estiver em uma empresa maior com uma solução de telefonia estabelecida, o assistente pode ajudá-lo a configurar um piloto do Business Voice para que você possa experimentar com alguns usuários antes de configurá-lo para todos. De qualquer forma, você pode começar a usar o Business Voice assim que o assistente for concluído!

É recomendável ler este artigo antes de iniciar o assistente. Quando estiver pronto, poderá abrir o assistente selecionando **Introdução** na página [Introdução ao Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice). Entre com a conta usada para criar sua assinatura ou outra conta que seja de um Administrador global.

> [!IMPORTANT]
> Atualmente o Business Voice está disponível no Canadá e no Reino Unido. Mais países e regiões estarão disponíveis em 2020.
>
> O Microsoft Teams e o Business Voice funcionam apenas quando as caixas de correio dos usuários estão localizadas no Microsoft 365.  Não há suporte para caixas de correio que estejam no servidor Exchange local.

<!-- After you've finished the wizard, here are a couple articles you can check out to see what you can do with Business Voice and learn how to customize it. If you don't want to customize anything, you're done! You can start using Business Voice right away.

* [Things to try with Business Voice](things-to-try.md)
* [Customize Business Voice](customize-business-voice.md)
-->

## <a name="emergency-services-location"></a>Local dos serviços de emergência

<table>
    <tr>
        <td>Se você quiser alterar o endereço de emergência, clique em <b>Editar</b> e digite um novo endereço. O endereço fornecido é validado para verificar se é legítimo e formatado corretamente para serviços de resposta a emergências. Se for válido, o endereço será atribuído a todos os usuários aos quais você atribuir um número na próxima etapa. Se você tiver funcionários em mais de um local, o tópico Personalizar o Business Voice mostra como adicionar e atribuir mais endereços de emergência após a conclusão do assistente do Guia de introdução.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

Se quiser saber mais, veja [O que são locais e endereços de emergência e encaminhamento de chamadas?](../what-are-emergency-locations-addresses-and-call-routing.md)

## <a name="company-phone-number"></a>Número do telefone comercial

<table>
    <tr>
        <td>Além de configurar um novo número de telefone local, você pode optar por comprar um número de chamada gratuita ou uma porta para um número existente no Microsoft 365. Caso opte por configurar um número de chamada gratuita, será necessário comprar um plano de chamada. Se desejar transferir um ou mais números para o Microsoft 365, você terá a opção de fazer a portabilidade no [centro de administração do Teams](https://admin.teams.microsoft.com) após concluir o assistente.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Caso opte por transferir um ou mais números de telefone existentes para o Microsoft 365, ainda haverá um número de telefone temporário no assistente. Está tudo bem. Depois de concluir o assistente e o processo de portabilidade, o número de telefone temporário será substituído pelo seu número de telefone.

## <a name="assigning-licenses-to-users"></a>Como atribuir licenças a usuários

<table>
    <tr>
        <td>Selecione as pessoas em sua organização que podem fazer ou receber chamadas telefônicas fora do Teams (por exemplo, ligar para um fornecedor). Você pode selecionar até o número máximo de licenças disponíveis no Business Voice. Se precisar de mais, adquira licenças adicionais depois de concluir o assistente.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Caso pretenda transferir números de telefone existentes para usuários individuais no Microsoft 365, isso será possível após a conclusão do assistente. Depois de concluir o processo de portabilidade, os números de telefones transferidos substituirão os números de telefone temporários selecionados pelo assistente.

## <a name="incoming-call-greeting"></a>Saudação de chamada de entrada

<table>
    <tr>
        <td>Você pode carregar um arquivo de som (MP3 ou WAV) de até 5 MB (megabytes) para usar como uma saudação ou pode digitar a saudação, e o Microsoft 365 usará a conversão de texto em fala para lê-la para um chamador. A saudação será a primeira coisa que os chamadores ouvirão ao ligar para o número de telefone da empresa. Talvez seja necessário soletrar as palavras ou usar a ortografia fonética para obter as pronúncias corretas.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>Menu de chamada e encaminhamento

<table>
    <tr>
        <td>Você pode encaminhar todas as chamadas para um usuário específico ou configurar um menu de chamada no qual é possível escolher opções. Se você criar um menu de chamada, pode especificar as opções que um chamador pode selecionar ao pressionar um número no teclado do telefone ou ao falar a opção por meio do comando de voz. Cada opção de menu pode ser encaminhada para um usuário. <br>
        Você pode escolher se deseja carregar um arquivo de som (MP3 ou WAV) de até 5 MB que fornece instruções para o chamador ou pode digitar as instruções. O Microsoft 365 usará a conversão de texto em fala para ler as instruções para o chamador. Talvez seja necessário soletrar as palavras ou usar a fonética para obter pronúncias corretas.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> O assistente de Introdução ajuda a configurar um menu de chamada simples para você começar a usá-la rapidamente. Se você tiver vários números de telefone nos quais que deseja configurar os menus de chamada, ou se quiser configurar menus de chamada mais complexos (também chamados de atendedores automáticos), poderá fazer isso seguindo as etapas em [Configurar um atendedor automático da Nuvem](set-up-auto-attendants.md) quando concluir o assistente.

<table>
    <tr>
        <td> <p>Na página <b>Visão geral</b>, o assistente do Guia de introdução considera tudo o que você inseriu e configura o Business Voice. Você pode ver quais números de telefone serão atribuídos aos usuários, olhar o menu de chamada, ouvir a saudação e muito mais. </p>
             <p>Configurar o Business Voice leva alguns minutos. Você pode clicar em <b>Concluído</b> e continuaremos a configurar o Business Voice em segundo plano, ou pode aguardar até que ele termine. Depois da conclusão, vá para <b>Voz</b> no <a href="https://admin.teams.microsoft.com" target="_blank">centro de administração do Teams</a> para configurar mais recursos do Business Voice.</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>