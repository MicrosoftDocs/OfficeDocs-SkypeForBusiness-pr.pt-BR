---
title: Implantar Salas do Microsoft Teams com Exchange local (Híbrido)
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams em um ambiente híbrido com Exchange local.
ms.openlocfilehash: 15936a805e45ce17ec35822bb02980b4d47499b8
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355610"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Implantar Salas do Microsoft Teams com Exchange local (Híbrido)

Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams em um ambiente híbrido com Exchange local e Microsoft Teams.
  
Se sua organização tiver uma combinação de serviços, com alguns locais hospedados e alguns hospedados online, sua configuração dependerá de onde cada serviço está hospedado. Este tópico aborda implantações híbridas para Salas do Microsoft Teams com Exchange hospedados no local. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final como documentado aqui e para outras opções de implantação.
  
## <a name="requirements"></a>Requisitos

Antes de implantar Salas do Microsoft Teams com Exchange local, certifique-se de ter atendido aos requisitos. Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).
  
Se você estiver implantando Salas do Microsoft Teams com Exchange local, você estará usando ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local. Essa conta será sincronizada com Microsoft 365 ou Office 365. Você deverá:
  
- Crie uma conta e sincronia a conta com Azure Active Directory.

- Habilitar a caixa de correio remota e as propriedades definidas.

- Atribua uma Microsoft 365 ou Office 365 licença.

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>Criar uma conta e sincronizar com Azure Active Directory

1. Na ferramenta Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse na pasta ou Unidade Organizacional na qual suas contas Salas do Microsoft Teams serão criadas, clique em Novo **e** em **Usuário**.

2. Digite o nome de exibição na **caixa Nome completo** e o alias na caixa Nome de **logon do** usuário. Click **Next**.

3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar **Senha nunca expira** é um requisito para Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmado, você precisará criar uma exceção para cada Salas do Microsoft Teams conta.
  
4. Depois de criar a conta, execute a sincronização do diretório. Quando estiver concluída, vá até a página usuários em seu Centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi sincronizada online.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. [Abra o Shell de Gerenciamento Exchange ou](/powershell/exchange/exchange-server/open-the-exchange-management-shell) conecte-se ao seu servidor Exchange usando o [PowerShell remoto.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. No Exchange PowerShell, crie uma caixa de correio para a conta (caixa de correio habilitada para a conta) executando o seguinte comando:

   ```PowerShell
   Enable-Mailbox ConferenceRoom01@contoso.com -Room
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).

3. No Exchange PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (Os organizadores da reunião recebem as decisões de reserva de sala diretamente sem intervenção humana.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)

   - RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdditionalResponse: "Esta é uma Microsoft Teams de reunião!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio de sala chamada ConferenceRoom01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma Microsoft 365 ou Office 365 licença

1. Conexão para Azure Active Directory. Para obter detalhes Azure Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. A conta de recurso precisa ter uma licença Microsoft 365 ou Office 365, ou Exchange e Microsoft Teams não funcionarão. Se você tiver a licença, precisará atribuir um local de uso à sua conta de recurso— isso determina quais SKUs de licença estão disponíveis para sua conta. Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Para obter instruções [detalhadas, consulte Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para validação, você deve ser capaz de usar qualquer cliente para fazer logoff nessa conta.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
