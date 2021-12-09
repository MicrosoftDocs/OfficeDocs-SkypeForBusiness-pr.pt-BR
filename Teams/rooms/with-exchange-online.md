---
title: Implantar as Salas do Microsoft Teams com o Exchange Online
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
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Exchange Online e Skype for Business Server local.
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355630"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implantar as Salas do Microsoft Teams com o Exchange Online

Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Exchange Online.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda implantações híbridas para Salas do Microsoft Teams com Exchange hospedado online. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final como documentado aqui e para outras opções de implantação.

## <a name="requirements"></a>Requisitos

Antes de implantar Salas do Microsoft Teams com Exchange Online, certifique-se de ter atendido aos requisitos. Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).
  
Para implantar Salas do Microsoft Teams com Exchange Online, siga as etapas abaixo. Verifique se você tem as permissões apropriadas para executar os cmdlets associados. 

   > [!NOTE]
   >  O módulo Azure Active Directory para [cmdlets](/powershell/azure/active-directory/overview) Windows PowerShell nesta seção (por exemplo, Set-MsolUser) foi testado na configuração de contas para Salas do Microsoft Teams dispositivos. É possível que outros cmdlets funcionem, no entanto, eles não foram testados neste cenário específico.

Se você implantou os Serviços de Federação do Active Directory (AD FS), talvez seja necessário converter a conta de usuário em um usuário gerenciado antes de seguir essas etapas e converter o usuário de volta em um usuário federado depois de concluir essas etapas.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Criar uma conta e definir as propriedades do Exchange

1. Inicie uma sessão Windows PowerShell remota em um computador e conecte-se Exchange Online seguinte:

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta se autenture em Salas do Microsoft Teams.

   Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se você estiver criando uma nova caixa de correio de recurso:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para melhorar a experiência de reunião, você precisará definir as propriedades Exchange na conta do usuário da seguinte forma:

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Adicionar um endereço de e-mail à conta de domínio local

1. Na ferramenta AD Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse no contêiner ou unidade organizacional em que suas contas Salas do Microsoft Teams serão criadas, clique em Novo e em **Usuário**. 
2. Digite o nome de exibição (- Identity ) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **Nome** completo e o alias na caixa Nome de **logon do** usuário. Click **Next**.
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar **Senha nunca expira é** um requisito para Skype for Business Server no Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmado, você precisará criar uma exceção para cada Salas do Microsoft Teams de usuário.
  
4. Clique em **Concluir** para criar a conta.
5. Depois de criar a conta, execute uma sincronização de diretório. Isso pode ser feito usando [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) no PowerShell. Quando isso for concluído, vá para a página usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma Microsoft 365 ou Office 365 licença

1. Primeiro, conecte-se ao Azure AD para aplicar algumas configurações de conta. Você poderá executar este cmdlet para se conectar. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview).

   > [!NOTE]
   > Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview)

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. A conta de usuário precisa ter uma licença Microsoft 365 ou Office 365 para garantir que Exchange funcionar. Se você tiver a licença, precisará atribuir um local de uso à sua conta de usuário— isso determina quais SKUs de licença estão disponíveis para sua conta. Você fará a atribuição em uma etapa a seguir.
3. Em seguida, use `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar uma lista de SKUs disponíveis para sua Microsoft 365 ou Office 365 organização.
4. Você pode adicionar uma licença usando o `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. Nesse caso, a licença Salas do Microsoft Teams Padrão está sendo aplicada.. 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
