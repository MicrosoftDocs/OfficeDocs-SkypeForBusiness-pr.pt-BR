---
title: Criar contas de recursos para salas e dispositivos compartilhados do Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este artigo para obter informações sobre como criar contas de recursos para salas e dispositivos compartilhados, incluindo Salas do Microsoft Teams, Salas do Teams no Surface Hub e hot-desking em exibições do Teams.
ms.openlocfilehash: eaa95efde1db01d3c7a346309f50eca2427af4e8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271706"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Criar e configurar contas de recursos para salas e dispositivos compartilhados do Teams

Este artigo fornece etapas para criar contas de recursos para espaços compartilhados e dispositivos, e inclui etapas para configurar contas de recursos para o Salas do Microsoft Teams no Windows, Salas do Teams no Android, Salas do Teams no Surface Hub e hot desking em exibições do Teams.

As contas de recursos do Microsoft 365 são contas de caixa de correio e do Teams que são dedicadas a recursos específicos, como uma sala ou projetor. Essas contas de recursos podem responder automaticamente a convites de reunião usando regras que você define quando são criadas. Por exemplo, se você tiver um recurso comum, como uma sala de conferência, poderá configurar uma conta de recurso para essa sala de conferência que aceitará ou recusará automaticamente convites de reunião, dependendo da disponibilidade do calendário. 

Cada conta de recurso é exclusiva para uma única instalação Salas do Microsoft Teams ou o Teams exibe a implementação de mesa quente.

> [!NOTE]
> Se estiver usando painéis do Microsoft Teams, Salas do Teams conta de recurso do Salas do Teams e dos painéis do Teams associados.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> Se você precisar habilitar sua conta de recurso para trabalhar com Skype for Business, consulte [Implantar Salas do Microsoft Teams com Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Antes de você começar

### <a name="requirements"></a>Requisitos

Dependendo do seu ambiente, você precisa de uma ou mais funções para criar contas de recursos.

|**Ambiente**|**Funções necessárias**|
|-----|-----|
|Azure Active Directory  <br/> |Administrador Global ou Administrador de Usuários  <br/> |
|Active Directory  <br/> |Administradores corporativos do Active Directory, administradores de domínio ou têm direitos delegados para criar usuários. Direitos de Sincronização do Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Administrador Global ou Administrador do Exchange   <br/> |
|Exchange Server  <br/> |Gerenciamento da Organização do Exchange ou Gerenciamento de Destinatários   <br/> |

Se você estiver criando contas de recursos para Salas do Teams, o UPN deverá corresponder ao endereço SMTP da conta de recurso. Consulte [Salas do Microsoft Teams requisitos antes](requirements.md) de implantar Salas do Teams.

### <a name="what-license-do-you-need"></a>De que licença você precisa?

Antes de criar uma conta de recurso do Microsoft 365, verifique qual tipo de licença ela precisa:

- **Reuniões do Teams** Se você quiser associar a conta de recurso a um dispositivo compartilhado, como uma sala do Microsoft Teams ou exibição do Teams com mesa quente, e usá-la para ingressar em uma reunião do Teams para que os participantes possam usá-la para apresentar vídeo e áudio por meio dela, você precisará de uma Licença de Sala de Reunião. Para obter mais informações sobre licenciamento para salas de reunião, consulte Licenciamento [de Sala de Reunião do Teams](rooms-licensing.md).

- **Chamadas PSTN** Se você quiser que o recurso faça ou receba chamadas de ou para um número de telefone externo (chamado de Rede Telefônica Pública Comunada ou chamada PSTN), você precisará de uma licença do Sistema de Telefonia do Microsoft 365 ou Microsoft 365 Business Voice. Você só precisa concluir a Etapa 1 na visão geral a seguir. Em seguida, [consulte licenças de complemento do Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obter mais informações.

- Se você estiver usando apenas uma conta de recurso para reservar um recurso que seja,&mdash;convide o recurso para sua reunião e aceite ou recuse automaticamente o convite, você não precisa atribuir uma licença à conta de recurso e só precisa concluir a&mdash;Etapa 1 na visão geral a seguir.  

## <a name="overview"></a>Visão geral

**Etapa 1 – Criar** [uma nova conta de recurso](#create-a-resource-account). Ou, se uma caixa de correio de sala já existir e você quiser convertê-la em uma conta de recurso, poderá modificar uma caixa de correio de sala [existente do Exchange](?tabs=existing-account#create-a-resource-account).

**Etapa 2 -**  Em seguida, [configure sua conta para](#configure-mailbox-properties) reuniões do Teams.

**Etapa 3 –**  Se a conta de recurso for associada a um dispositivo compartilhado, como as exibições do Teams com o hot desking, desative a [expiração da senha](#turn-off-password-expiration).

**Etapa 4 –**  Por fim, [atribua uma licença de sala de reunião](#assign-a-meeting-room-license) para que a conta possa acessar o Microsoft Teams.

Depois de criar e configurar suas contas de recursos, [](#next-steps) confira As próximas etapas para examinar tarefas de configuração adicionais, incluindo grupos de distribuição, capacidade de rede e chamadas.

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

> [!TIP]
> Ao nomear suas contas de recurso, recomendamos usar uma convenção de nomenclatura padrão para o início do endereço de email. Isso ajudará na criação de grupos dinâmicos para facilitar o gerenciamento no Azure Active Directory. Por exemplo, você pode usar "mtr-" para todas as contas de recursos que serão associadas a Salas do Microsoft Teams.

> [!TIP]
> Recomendamos que você crie todas as contas de recursos usando o Exchange Online e o Azure Active Directory.

Crie uma conta de recurso usando um método de uma das seguintes guias:

#### <a name="in-microsoft-365-admin-center"></a>[**Em Centro de administração do Microsoft 365**](#tab/m365-admin-center)

1. Acesse o Centro de administração do Microsoft 365.

2. Forneça as credenciais de administrador para seu locatário do Microsoft 365.

3. Vá para **Recursos** no painel esquerdo e selecione Salas **& equipamento**. Se essas opções não estiverem disponíveis no painel esquerdo, talvez seja necessário selecionar **Mostrar tudo** primeiro.

4. Selecione **Adicionar uma caixa de correio de recurso** para criar uma nova conta de sala. Insira um nome de exibição e um endereço de email para a conta, selecione **Adicionar** e, em seguida, **selecione Fechar**.

5. Por padrão, as contas de recurso são definidas com as seguintes configurações:

    - Permitir reuniões repetidas
    - Recusar reuniões automaticamente fora dos limites a seguir
      - Janela de reserva (dias): 180
      - Duração máxima (horas): 24
    - Aceitar automaticamente solicitações de reunião

    Se você quiser alterá-las, selecione **Definir opções de agendamento** antes de selecionar **Fechar**. Se você quiser alterá-los mais tarde, vá  >  para Salas de Recursos **& equipamento**, selecione a conta de recurso. Em Seguida, **em Opções de Reserva**, selecione **Editar**.

6. Vá para **Usuários** > **Ativos e** selecione a sala que você criou para abrir o painel de propriedades.

7. Em seguida, atribua uma senha à conta de recurso. No painel, selecione **Redefinir senha**.
 
8. Exigir que os usuários alterem a senha em um dispositivo compartilhado causará problemas de entrada. **Desmarque Exigir que esse usuário altere a senha ao** entrar pela primeira vez e selecione **Redefinir**.

9. Na seção **Licenças e Aplicativos** , defina **Selecionar local** para o país ou região em que o dispositivo será instalado. Em seguida, selecione a licença que você deseja atribuir, como a Sala de Reunião, e selecione **Salvar alterações**. A licença pode variar dependendo da sua organização.

Para alterar as configurações da caixa de correio do recurso, consulte [Configurar propriedades da caixa de correio](#configure-mailbox-properties) ou use o Centro de administração do Exchange.

Talvez você também precise aplicar políticas de largura de banda ou políticas de reunião a essa conta. Confira [As próximas etapas](#next-steps) para obter mais informações.

#### <a name="with-exchange-online"></a>[**Com Exchange Online**](#tab/exchange-online)

1. Conecte-se [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Por padrão, as caixas de correio de sala não têm contas associadas. Adicione uma conta ao criar uma caixa de correio de sala para que ela possa ser autenticada com o Microsoft Teams.

    Se você estiver criando uma nova caixa de correio de recurso:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

    - Conta: ConferenceRoom01@contoso.com
          
    - Nome: ConferenceRoom01
        
     - Alias: ConferenceRoom01
        
     - Senha da conta: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Se você não estiver em uma configuração híbrida do Exchange, poderá continuar para a próxima etapa, Configurar [as propriedades da caixa de correio](#configure-mailbox-properties).

Se você estiver em uma configuração híbrida do Exchange, precisará adicionar um endereço de email para sua conta de domínio local. Consulte [Sincronizar diretórios de contas de usuário Office 365 locais e locais](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obter mais informações.

#### <a name="with-exchange-server"></a>[**Com Exchange Server**](#tab/exchange-server)

  1. Conecte-se ao Shell de Gerenciamento do Exchange. [Abra o Shell de Gerenciamento do Exchange](/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [conecte-se ao servidor Exchange usando o PowerShell remoto](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Para criar uma nova caixa de correio de sala:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

   - Conta: ConferenceRoom01@contoso.com
  
   - Nome: ConferenceRoom01

   - Alias: ConferenceRoom01

   - Senha da conta: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificar uma caixa de correio de sala existente do Exchange**](#tab/existing-account)

Para modificar uma caixa de correio de sala existente para se tornar uma conta de recurso, use a seguinte sintaxe:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias ConferenceRoom02 e define a senha como 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Se você estiver em uma configuração híbrida do Exchange, também precisará adicionar um endereço de email para sua conta de domínio local. Consulte [Sincronizar diretórios de contas de usuário Office 365 locais e locais](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obter mais informações.

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se você estiver criando essa conta para a Sala do Teams no Surface Hub, também deverá habilitar o ActiveSync nessa conta. Isso permitirá que você envie emails diretamente do Surface Hub, que você pode usar para recursos como o Whiteboard. Confira [a aplicação de políticas activeSync a contas de dispositivo (Surface Hub)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) para saber mais.

---

> [!IMPORTANT]
> Se você estiver usando apenas essa conta de recurso para reservar espaço e aceitar ou recusar convites automaticamente, você concluiu a configuração. Se você estiver usando essa conta de recurso para chamadas PSTN, consulte [licenças](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) de complemento do Microsoft Teams para determinar de qual licença ela precisa.
>
> Continue para a próxima seção somente se a conta de recurso for para um Salas do Teams no Windows, Salas do Teams no Android, Salas do Teams no Surface Hub ou uma exibição do Teams com mesa dinâmica.

## <a name="configure-mailbox-properties"></a>Configurar propriedades da caixa de correio

No Exchange PowerShell, online ou local, defina as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:

- **AutomateProcessing: `AutoAccept`** Os organizadores da reunião recebem a decisão de reserva da sala diretamente sem intervenção humana.

- **AddOrganizerToSubject: `$false`** O organizador da reunião não é adicionado ao assunto da solicitação de reunião.

- **DeleteComments: `$false`** Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada. Isso é necessário para processar equipes externas e reuniões de terceiros para fornecer uma experiência de Ingresso no One Touch.

- **DeleteSubject: `$false`** Mantenha o assunto das solicitações de reunião recebidas.

- **ProcessExternalMeetingMessages: `$true`** Especifica se as solicitações de reunião devem ser processadas que se originam fora da organização do Exchange. Necessário para reuniões externas do Teams e [reuniões de terceiros](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Garante que o sinalizador privado que foi enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.

- **AddAdditionalResponse: `$true`** O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.

- **AdditionalResponse: "Esta é uma sala de reunião do Microsoft Teams!"** O texto adicional a ser adicionado à resposta de aceitação da reunião.

Este exemplo define essas configurações em uma caixa de correio de sala chamada ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Desativar a expiração da senha

Se a senha da conta de recurso expirar, o dispositivo não entrará após a data de validade. Em seguida, a senha precisará ser alterada para a conta de recurso e, em seguida, atualizada em cada dispositivo. Para evitar isso, você pode desativar a expiração da senha.
  
> [!NOTE]
> A **configuração de senha nunca expira** é um requisito para dispositivos compartilhados do Microsoft Teams. Se suas regras de domínio proibirem senhas que não expiram, você precisará criar uma exceção para cada conta de recurso de dispositivo do Teams.

Siga as etapas em uma das seguintes guias para desativar a expiração da senha:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Primeiro, conecte-se ao Active Directory PowerShell:

```PowerShell
   Connect-AzureAD
```

Em seguida, consulte [Definir uma senha para nunca expirar](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

Este exemplo define a senha para a conta ConferenceRoom01@contoso.com nunca expirar.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Conecte-se ao MSOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Para obter detalhes sobre o Active Directory, [consulte O Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Defina a senha para nunca expirar usando a seguinte sintaxe:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Este exemplo define a senha para a conta ConferenceRoom01@contoso.com nunca expirar.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (local)**](#tab/active-directory1-password/)

1. Conecte-se ao Active Directory PowerShell:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Para obter detalhes sobre o Active Directory PowerShell, consulte [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. Defina a senha para nunca expirar usando a seguinte sintaxe:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Este exemplo define a senha para a conta ConferenceRoom01@contoso.com nunca expirar.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Atribuir uma licença de sala de reunião

A conta de recurso precisa de uma licença do Microsoft 365 ou Office 365 para entrar no Microsoft Teams.

> [!NOTE]
> Salas do Microsoft Teams Padrão e Salas do Microsoft Teams Premium são os dois SKUs disponíveis para dispositivos de sala de reunião compartilhados, incluindo Salas do Teams. Uma licença de sala de reunião é necessária para exibições do Teams com mesa quente. Para obter mais informações, consulte [licenciamento da sala de reunião do Teams](rooms-licensing.md).

Para atribuir licenças usando o Centro de administração do Microsoft 365, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users). Para atribuir licenças usando Azure AD, consulte uma das seguintes guias:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Conectar-se ao Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Para obter detalhes sobre o Active Directory, consulte [o PowerShell do Azure Active Directory para Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Atribua um local de uso à sua conta de recurso usando o `Set-AzureADUser` cmdlet. Isso determina quais SKUs de licença estão disponíveis.

    Neste exemplo, o usuário está localizado no Estados Unidos (EUA):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. Em seguida, use `Get-AzureADSubscribedSku` para recuperar uma lista de SKUs disponíveis para o Microsoft 365 ou Office 365 organização.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Para atribuir a licença, use `Set-AzureADUser` o cmdlet e converta a ID de SKU da licença (consulte a etapa 2) em um objeto de tipo de licença do PowerShell. Em seguida, atribua esse objeto à conta de recurso. No exemplo a seguir, a ID de SKU de licença é 6070a4c8-34c6-4937-8dfb-39bbc6397a60 e é atribuída à conta conferenceroom01@contoso.com:

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. Conecte-se ao MSOnline PowerShell.

   ```PowerShell
   Connect-MsolService
   ```

    Para obter detalhes sobre o Active Directory, [consulte O Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Atribua um local de uso à sua conta de recurso usando o `Set-MsolUser` cmdlet. Isso determina quais SKUs de licença estão disponíveis.

    Neste exemplo, o usuário está localizado no Estados Unidos (EUA).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    Em seguida, você pode `Get-MsolAccountSku` usar para recuperar uma lista de SKUs disponíveis para o Microsoft 365 ou Office 365 organização.

4. Para atribuir a licença, use o `Set-MsolUser` cmdlet. Neste exemplo, a licença "contoso:MEETING_ROOM" é atribuída à conta conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Para validar a criação da conta e a atribuição de licença, entre em qualquer Cliente do Teams usando a conta que você criou.

## <a name="next-steps"></a>Próximas etapas

### <a name="meeting-policies"></a>Políticas de reunião

Talvez seja necessário aplicar políticas personalizadas de rede, largura de banda ou reunião a essa conta. Para obter mais informações sobre políticas de rede e largura de banda, consulte [Configurações de política de reunião para áudio & vídeo](/microsoftteams/meeting-policies-audio-and-video). Por Salas do Teams, recomendamos que você defina a largura de banda da política de reunião como 10 Mbps.

Para fins de colaboração, ative PowerPoint Live, quadro de comunicações e anotações compartilhadas. É recomendável que você habilite a configuração de política de reunião "Reunir agora em reuniões privadas". Talvez você queira criar uma política de reunião para ajustar os participantes e as configurações de convidado para Salas do Teams. Por exemplo, examine as configurações de lobby, como quais participantes admitirão automaticamente as reuniões. Para obter mais informações sobre as políticas de reunião do Teams, consulte [Gerenciar políticas de reunião no Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Chamadas

Não há requisitos exclusivos para habilitar a chamada com contas de recursos. Você habilita a conta de recurso para chamada da mesma maneira que habilita um usuário normal.

> [!NOTE]
> Recomendamos desativar a caixa postal para dispositivos compartilhados atribuindo uma política de chamada às contas de recursos do dispositivo. Consulte [Chamadas e encaminhamento de chamadas no Teams](../teams-calling-policy.md) para obter mais informações.

### <a name="configure-distribution-groups-for-teams-calendar"></a>Configurar grupos de distribuição para o Calendário do Teams

Para organizar seus locais de sala de reunião, você pode adicionar suas contas de recursos do dispositivo aos grupos de distribuição do Exchange. Por exemplo, se você tiver escritórios em três locais geográficos diferentes, poderá criar três grupos de distribuição e adicionar as contas de recursos apropriadas a cada local. Para obter mais informações, consulte [Criar uma lista de salas](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

### <a name="configure-places-for-outlook-calendar"></a>Configurar locais para Calendário do Outlook
Para que os locais de sala de reunião apareçam no Localizador de Sala do Outlook, você precisa usar o cmdlet Set-Place Exchange PowerShell. Além de Set-Place popular o Localizador de Sala no Outlook, ele também permite que você adicione metadados adicionais, como a capacidade da sala ou do andar de construção em que a sala está. Para obter mais informações, consulte [Set-Place](/powershell/module/exchange/set-place).

## <a name="related-articles"></a>Artigos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Salas do Microsoft Teams licenciamento](rooms-licensing.md)
