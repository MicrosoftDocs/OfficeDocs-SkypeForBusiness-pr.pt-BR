---
title: Alterar números de telefone Audioconferência ponte
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Conheça as etapas necessárias para atribuir um novo número de telefone de serviço à ponte de conferência para expandir a cobertura para seus usuários.
ms.openlocfilehash: 0433577334dca5f84854ba1cdc14b81e4ec37e63
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674773"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Alterar os números de telefone em sua ponte de Audioconferência

Quando você compra **Audioconferência** licenças, a Microsoft está hospedando sua ponte de audioconferência para sua organização. A ponte de audioconferência fornece números de telefone de discagem de locais diferentes para que os organizadores e participantes da reunião possam usá-los para ingressar em reuniões Skype for Business ou Microsoft Teams usando um telefone.

Além dos números de telefone já atribuídos à ponte de conferência, você pode obter números de serviço adicionais [(números](./getting-service-phone-numbers.md) de chamada tarifada e gratuita usados para audioconferência) de outros locais e atribuí-los à ponte de conferência para que você possa expandir a cobertura para seus usuários.

> [!NOTE]
> Para poder atribuir/cancelar a atribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de "*serviço*". Você pode ver o  >  tipo de número que ele é navegando até Voz **Telefone** números no centro de administração do Microsoft Teams e olhando na coluna Tipo **de** Número. Microsoft 365 ou Office 365 os Créditos de Comunicações devem ser configurados primeiro para que os usuários discem para a ponte em um número de chamada gratuita.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência

> [!NOTE]
> Exceto quando for chamado caso contrário, todas essas etapas devem ser executadas no centro Microsoft Teams administrador.

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Etapa 1 – Atribuir o novo número de telefone à ponte de audioconferência

1. No painel de navegação esquerdo, vá para **Números Telefone** >  **Voz**.

2. Selecione o número de telefone na lista e clique em **Editar**.

3. Na página **Editar**, em **Atribuído a, expanda** a lista suspensa e selecione **Aplicar ponte de conferência** > .

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Etapa 2 – Alterar o número de telefone padrão da ponte de conferência (opcional)

O número de telefone padrão da ponte de conferência define a ID do chamador que será usada quando uma chamada de saída for feita por um participante ou pelo organizador de dentro de uma reunião.

Somente um número de chamada tarifada de serviço pode ser definido como o número padrão para sua ponte de conferência; **os números de chamada gratuita de serviço não podem ser definidos como o número padrão da ponte de conferência**. Se você estiver atribuindo um número de chamada tarifada de serviço e quiser defini-lo como o novo número padrão para sua ponte de audioconferência, execute estas etapas:

1. No painel de navegação esquerdo, vá para pontes **de Conferência** > **de Reuniões**.

2. Realce o número de chamada tarifada de serviço que você deseja configurar como o padrão.

3. Selecione **Definir como padrão**.

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Etapa 3 – Alterar os números de telefone padrão incluídos nos convites de reunião de usuários (opcional)

Consulte [Definir os números de telefone incluídos nos convites Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Você também pode definir números de telefone adicionando-os à *TeamsAudioconferencingpolicy* e atribuindo a política aos usuários. Os números de telefone de chamada tarifada e gratuita adicionados à política têm precedência sobre os números de telefone definidos individualmente para os usuários por meio do painel de configurações de audioconferência. Se nenhum número de telefone for adicionado à *Teamsaudioconferencingpolicy*, o número de telefone definido individualmente para os usuários por meio do painel de configurações de audioconferência será exibido em Microsoft Teams de reunião. [Audioconferência configurações de política para números de chamada tarifada](audio-conferencing-toll-free-numbers-policy.md) e gratuita têm mais informações.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Etapa 4 – Atualizar convites de reunião existentes de usuários usando o Serviço de Migração de Reunião (opcional)

Para as próximas duas etapas, você precisará começar a Windows PowerShell.

Se você atualizou os números de telefone padrão incluídos nos convites da reunião para alguns ou todos os seus usuários, opcionalmente, você pode atualizar convites de reunião que já foram enviados aos usuários em sua organização antes que seus números de telefone padrão fossem alterados usando o Serviço de Migração de Reunião. Para obter informações adicionais, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

- Execute o MMS (Serviço de Migração de Reunião) para os usuários que tiveram seus números de telefone padrão alterados na Etapa 2. Para isso, execute o seguinte comando:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Você também pode visualizar o status de migração da reunião. Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência

Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão mais ingressar nas reuniões usando aquele número de telefone. Como o número de telefone está mudando, é importante atualizar todos os usuários que podem ter um número de telefone como número de telefone padrão (se houver) e atualizar seus convites de reunião existentes antes que o número de telefone seja não atribuído da ponte de audioconferência.

Se o número de telefone for removido sem atualizar os usuários e suas reuniões, seus convites de reunião existentes poderão conter um número de telefone que não funcionará para ingressar em suas reuniões.

Para as primeiras três etapas, você deverá iniciar o Windows PowerShell. Para ver como fazer isso, clique [em Quer saber como gerenciar com Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Etapa 1 – Atualizar usuários que têm o número de telefone a ser não atribuído como um de seus números padrão

Substitua o número de chamada tarifada ou gratuita padrão para todos os usuários que têm o número a ser não atribuído como um número padrão e inicie o processo de reagendamento de suas reuniões. Para isso, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >Você também pode alterar o número de chamada tarifada ou gratuita padrão de usuários Microsoft Teams centro de administração. No entanto, isso não reagenda automaticamente suas reuniões.

 Para obter informações adicionais, consulte Definir os números de telefone [incluídos em convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou Definir os números de telefone [incluídos em convites no Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > [!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell

Todas as reuniões serão reagendadas quando não houver operações *no estado Pendente* *ou Em* Andamento.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Etapa 3 – Cancelar a atribuição do número de telefone antigo da ponte de audioconferência

Use o cmdlet Unregister-CsOnlineDialInConferencingServiceNumber para cancelar o registro de um número de chamada tarifada ou gratuita de uma ponte de conferência

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

Observação: para localizar a ID da Ponte de Conferência, execute o seguinte PowerShell: Get-CsOnlineDialInConferencingBridge.

   > [!IMPORTANT]
   > Depois que um número de telefone não for atribuído de uma ponte de audioconferência, o número de telefone não estará mais disponível para que os usuários ingressem em reuniões novas ou existentes.

### <a name="save-time-and-automate"></a>Economizar tempo e automatizar

Para economizar tempo automatizando esse processo, você pode usar os cmdlets [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) ou **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Use o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.

  - Para mudar o número de chamada gratuita padrão de um usuário, execute:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.

    > [!NOTE]
    > Para localizar a BridgeID, use **Get-CsOnlineDialInConferencingBridge**.

  - Para definir 8005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para mudar o número de chamada gratuita padrão de todos os usuários que têm 8005551234 como seu número de chamada gratuita padrão para 8005551239 e reagendar automaticamente suas reuniões, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA como 8005551234 e reagendar automaticamente suas reuniões, execute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > O local usado acima precisa corresponder às informações de contato dos usuários que estão definidas no Centro de administração do Microsoft 365.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="the-unassign-button-isnt-available"></a>O botão Cancelar a atribuição não está disponível

Você deseja cancelar a atribuição de um número, mas o botão não está disponível e, ao passar o mouse sobre ele, você será redirecionado para entrar em contato com o Suporte com a seguinte mensagem: "Números padrão ou compartilhados não podem ser atribuídos da ponte. Para cancelar a atribuição de números de pedágio dedicados, entre em contato com o suporte.".

Para obter mais informações sobre as pontes, execute o seguinte Powershell:

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

O resultado, além de outras informações, como Identidade, Nome e Região, também deve conter DefaultServiceNumber.

**Exemplo**, para cancelar a atribuição, o DefaultServiceNumber "8005551234"

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234
```

## <a name="about-windows-powershell"></a>Sobre Windows PowerShell

Com Windows PowerShell você pode gerenciar usuários e o que eles são ou não têm permissão para fazer. Windows PowerShell pode ajudá-lo a gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, especialmente quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em vez de usar apenas o Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

- [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Tópicos relacionados

[Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md)
