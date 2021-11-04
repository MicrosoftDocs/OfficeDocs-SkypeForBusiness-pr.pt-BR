---
title: Provisionamento Skype contas do Sistema de Sala em Microsoft 365 e Office 365
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para saber mais sobre o provisionamento Skype contas do Sistema de Sala em Microsoft 365 ou Office 365.
ms.openlocfilehash: 1f4262453735baa08e16e7da03909e48ef12f4ff
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758113"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Provisionamento Skype contas do Sistema de Sala em Microsoft 365 e Office 365
 
Leia este tópico para saber mais sobre o provisionamento Skype contas do Sistema de Sala em Microsoft 365 ou Office 365.
  
A seção a seguir aborda Skype provisionamento da conta do Sistema de Sala.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 e Office 365 pré-requisitos

Seu locatário online deve atender aos seguintes requisitos:
  
- O Microsoft 365 ou Office 365 deve incluir o Skype for Business Online 2, ou Office 365 E1, E3 ou E5. <br/>Para obter detalhes sobre Skype for Business Online, consulte o [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).
    
- Seu locatário deve ter o recurso de conferência de Skype for Business habilitado.
    
- Seu locatário deve ter Exchange Online habilitado. 
    
- O administrador remoto do locatário deve ter o seguinte acesso ao PowerShell:
    
  - Exchange Acesso remoto do PowerShell
    
  - Skype for Business Acesso ao PowerShell Remoto Online
    
  - Windows Azure Active Directory módulo para Windows PowerShell acessar Microsoft 365 ou Office 365 de diretório
    
Para a Skype room, o licenciamento a seguir é necessário:
  
- Uma Skype for Business online 2 ou Office 365 E1 ou E3 é necessária para habilitar Skype Reuniões.
    
- Para dar direito à sala com o recurso Enterprise Voice para que a sala possa ser habilitada com um número de telefone, um plano 2 do Skype for Business Online com Sistema de Telefonia licença ou Office 365 E5 é necessário (1).
    
- Se você precisar de recursos de discagem de uma reunião, precisará de uma audioconferência e Sistema de Telefonia licença.  Se você precisar de recursos de discagem de uma reunião, precisará de um Plano de Chamada doméstico ou doméstico e internacional. 
    
- Uma Exchange Online não é necessária para a conta Skype Room porque a conta deve ser configurada como uma conta de caixa de correio de recurso.
    
## <a name="provisioning-overview"></a>Visão geral do provisionamento

O diagrama a seguir fornece uma visão geral do fluxo Skype de provisionamento da conta do Sistema de Sala.
  
![Skype Etapas de Provisionamento do Sistema de Sala.](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar uma nova sala de conferência

Você pode já ter uma caixa de correio de sala de recursos Exchange que fornece o recurso de agendamento ou pode estar criando uma caixa de correio de recurso pela primeira vez para facilitar a implantação do sistema de sala Skype sala. Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário. As Exchange Online provisionamento e Skype for Business provisionamento fornecem orientações para ambos os tipos de contas. Por exemplo, digamos que você tenha as duas salas a seguir e gostaria de implantar o Skype Room System para ambas:
  
- Conta de Caixa de Correio de Recurso existente: confrm1@contoso.onmicrosoft.com
    
- Nova Conta de Caixa de Correio de Recurso: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online provisionamento

Primeiro, conecte-se ao Exchange Online PowerShell seguindo as instruções no tópico, Conexão [para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
Para definir uma conta de caixa de correio de sala de recursos existente para Skype Room System, execute os seguintes comandos no Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para criar uma nova conta Exchange de caixa de correio de recurso Skype Room System, execute os seguintes comandos no Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Os comandos anteriores configuram ou criam uma nova conta Exchange de caixa de correio de recurso para Skype uso do Sistema de Sala habilitando a conta.
  
Depois de criar a caixa de correio, você pode usar o cmd Exchange Online let Set-CalendarProcessing no PowerShell para configurar a caixa de correio. Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes

## <a name="assigning-a-skype-for-business-online-license"></a>Atribuir uma licença Skype for Business Online

Agora você pode atribuir uma licença do Skype for Business Online (Plano 2) ou do Skype for Business Online (Plano 3) usando o portal administrativo do Microsoft 365 conforme descrito em Atribuir ou [remover licenças](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) para o Microsoft 365 para empresas [ou](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)no licenciamento de complementos do Skype for Business. 
  
Depois de atribuir uma licença para Skype for Business Online, você poderá fazer logoff e validar se a conta está ativa usando qualquer Skype for Business cliente.
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Provisionamento online

Depois que uma conta de caixa de correio de sala de recursos tiver sido criada e habilitada, conforme mostrado anteriormente, e você tiver licenciado a conta do Skype For Business Online, a conta será sincronizada da floresta Exchange Online para a floresta Skype for Business Online usando a floresta Windows Azure Active Directory. As etapas a seguir são necessárias para provisionar a conta Skype Room System no pool Skype for Business Online. Essas etapas são as mesmas para uma conta de caixa de correio de recurso existente ou para uma conta recém-criada (confrm1 ou confrm2), pois depois de habilitadas no Exchange Online, ambas as contas serão sincronizadas com o Skype for Business Online da mesma maneira:
  
1. Criar uma sessão do PowerShell remoto. Observe que você precisará baixar o [módulo Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Para habilitar uma Skype do Sistema de Sala para Skype for Business, execute o seguinte comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Você pode obter o endereço RegistrarPool onde seus usuários Skype for Business estão em casa de uma de suas contas existentes usando o seguinte comando para retornar essa propriedade:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>A autenticação multifafação (MFA) não é suportada para contas Skype Room System. 

## <a name="password-expiration"></a>Expiração da senha

Em Microsoft 365 ou Office 365, a política de expiração de senha padrão para todas as suas contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente. Para Skype contas do Sistema de Sala, você pode selecionar a configuração Senha nunca expira com as etapas a seguir.
  
1. Crie uma Windows Azure Active Directory usando as credenciais de administrador global do locatário.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Definir a configuração Senha nunca expira para a conta de sala Skype sala do Sistema de Sala criada anteriormente usando o seguinte comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obter mais informações, [consulte Configurar seu computador para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer Skype for Business cliente para entrar na conta criada.