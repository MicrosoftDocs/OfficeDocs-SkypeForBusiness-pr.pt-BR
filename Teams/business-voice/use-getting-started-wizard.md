---
title: Usar o assistente do Guia de Introdução para configurar o Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 443a59513d3a3151bdcc83250bf40ec4ac4398bb
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412618"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>Usar o assistente do Guia de Introdução para configurar o Business Voice

> [!IMPORTANT]
> As informações contidas neste artigo se aplicam apenas ao Business Voice **com** plano de chamada. O Business Voice com o plano de chamada só está disponível em alguns países e regiões. Antes de ler este artigo, verifique a [Disponibilidade do Business Voice em países e regiões](country-region-availability.md) para ver se seu país ou região é compatível com o Business Voice com plano de chamada.
>
> Se o locatário estiver localizado em um país ou região que não é compatível com o plano de chamada, confira [Obter ajuda de um revendedor ou parceiro da Microsoft](reseller-partner-support.md).

O Assistente do Guia de Introdução do Microsoft 365 Business Voice permite que você seja configurado rapidamente para fazer e receber chamadas telefônicas no Microsoft Teams. Se você estiver começando a trabalhar em uma empresa pequena, o assistente consegue colocá-lo para trabalhar em alguns minutos com números de telefone, menus de chamadas, saudações e muito mais. Se você é um grande negócio com uma solução de telefonia estabelecida, o assistente pode ajudá-lo a configurar um piloto para que alguns usuários possam experimentar o Business Voice antes de lançá-lo para todos. De qualquer forma, você pode começar a usar o Business Voice assim que o assistente for concluído!

É recomendável ler este artigo antes de iniciar o assistente. Quando estiver pronto para executar o assistente, selecione **Introdução** na página [Introdução ao Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice). Entre usando a conta que você usou para criar sua assinatura ou outra conta que seja um Administrador Global.

> [!IMPORTANT]
> O Microsoft Teams e o Business Voice funcionam apenas quando as caixas de correio dos usuários estão localizadas no Microsoft 365.  Eles não oferecem suporte a caixas de correio no Servidor Exchange local.
>
> O Assistente de introdução não suporta implantações híbridas do Skype for Business. Se você tiver uma implantação híbrida do Skype for Business e quiser configurar ao Business Voice, consulte [Configurar o sistema telefônico na sua organização](../setting-up-your-phone-system.md).

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

Se você não quiser personalizar nada imediatamente, pronto! Você pode começar usando o Business Voice imediatamente.

## <a name="emergency-services-location"></a>Local dos serviços de emergência

<table>
    <tr>
        <td>Se você quiser alterar o endereço de emergência, clique em <b>Editar</b> e, em seguida, insira um novo endereço. O endereço que você fornece é validado para garantir que seja legítimo e corretamente formatado para serviços de resposta a emergências. Esse endereço será atribuído a todos os usuários aos quais você atribuir um número na próxima etapa. Se você tiver funcionários em mais de um local, confira <a href="./customize-business-voice.md">Personalização do design do Business Voice</a> para adicionar e atribuir mais endereços de emergência após preparar o assistente do Guia de Introdução.</td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

Para saber mais, confira [O que são locais de emergência, endereços e roteamento de chamadas](../what-are-emergency-locations-addresses-and-call-routing.md)?

## <a name="company-phone-number"></a>Número do telefone comercial

<table>
    <tr>
        <td>Além de um novo número de telefone local, você pode comprar um número de chamada gratuita ou portar um número existente para o Microsoft 365. Para configurar um número de chamada gratuita, você precisa comprar Créditos de Comunicações. Para portar um ou mais números para o Microsoft 365, vá para o <a href="https://admin.teams.microsoft.com">centro de administração do Teams</a> após concluir o assistente.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Se você portar um número de telefone existente para o Microsoft 365, você continuará vendo um número de telefone temporário no assistente. Isso é esperado. Depois de concluir o assistente e o processo de portabilidade, o número de telefone temporário será substituído pelo número pré-existente.

## <a name="user-licenses"></a>Licenças de usuário

<table>
    <tr>
        <td>Para atribuir licenças de usuário, selecione as pessoas em sua organização que precisam fazer ou receber chamadas telefônicas fora do Teams (como ligar para um fornecedor). Você pode atribuir quantas licenças do Business Voices tiver disponível. Se você precisar de mais, poderá comprar licenças adicionais após a conclusão do assistente.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Você pode portar números de telefone existentes para o Microsoft 365 após a conclusão do assistente. Depois de concluir o processo de portabilidade, os números de telefones portados substituirão os números de telefone temporários fornecidos pelo assistente.

## <a name="incoming-call-greeting"></a>Saudação de chamada recebida

<table>
    <tr>
        <td>Você pode carregar um arquivo de som (MP3 ou WAV) de até 5 Megabytes (MB) para usar como uma saudação de chamada ou digitar sua saudação, e o Microsoft 365 usará a conversão de texto em fala para lê-lo no chamador. A saudação será a primeira coisa que os chamadores ouvirão quando ligar para o número de telefone da sua empresa. Para conversão de texto em fala, pode ser necessário usar ortografia fonética para corrigir as pronúncias.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>Menu de chamada e encaminhamento

<table>
    <tr>
        <td>Você pode encaminhar todas as chamadas para um usuário específico ou pode configurar um menu no qual o chamador pode escolher opções. Se você criar um menu de chamada, especifique as opções que o chamador poderá selecionar por voz ou pressionando um número no teclado do telefone. Cada opção de menu pode encaminhar chamadas para um usuário específico.<br><br>
        Você pode enviar um arquivo de som (MP3 ou WAV) de até 5 MB que forneça instruções ao chamador ou digite as instruções. O Microsoft 365 usará a conversão de texto em fala para lê-los no chamador. Talvez seja necessário soletrar as palavras ou usar a fonética para obter pronúncias corretas.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> O assistente de Introdução ajuda a configurar um menu de chamada simples para você começar a usá-la rapidamente. Se você tiver vários números de telefone nos quais que deseja configurar os menus de chamada, ou se quiser configurar menus de chamada mais complexos (também chamados de atendedores automáticos), confira [Configurar um atendedor automático da Nuvem](set-up-auto-attendants.md) após concluir o assistente.

<table>
    <tr>
        <td> <p>O Assistente do Guia de Introdução utiliza as informações inseridas e configura o Business Voice. Na página <b>Visão geral</b>, você pode ver quais números de telefone são atribuídos aos usuários, consultar o menu de chamadas, ouvir a saudação e muito mais.</p>
             <p>A instalação leva alguns minutos. Se você selecionar <b>Concluído</b>, continuaremos a configurar a Business Voice em segundo plano. Ou aguarde até que a instalação seja concluída. Depois da conclusão, vá para <b>Voz</b> no <a href="https://admin.teams.microsoft.com" target="_blank">centro de administração do Teams</a> para configurar mais recursos do Business Voice.</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
