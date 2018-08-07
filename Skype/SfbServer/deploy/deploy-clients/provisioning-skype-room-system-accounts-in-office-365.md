---
title: Provisionamento das contas do Sistema de Salas do Skype no Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.
ms.openlocfilehash: b248168870366db8f685db48197badb3bacf935f
ms.sourcegitcommit: 4660539cf0a6f7fde5de0a68bc4866089962ce80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2018
ms.locfileid: "22102050"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Provisionamento das contas do Sistema de Salas do Skype no Office 365
 
Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.
  
A seção a seguir aborda a conta do sistema de sala do Skype provisionamento para um locatário do Office 365.
  
## <a name="office-365-prerequisites"></a>Pré-requisitos do Office 365

Seu locatário online deve cumprir os seguintes requisitos:
  
- O plano do Office 365 deve incluir Skype para negócios Online plano 2, 3 do plano, ou Office 365 E1, E3 ou E5.
    
- Seu inquilino deve ter a capacidade de conferência do Skype para negócios habilitado.
    
- Seu locatário deve ter o Exchange Online habilitado.   
    
- O administrador remoto do seu locatário deve ter o seguinte acesso PowerShell: 
    
  - Acesso PowerShell remoto do Exchange
    
  - Skype para acesso de negócios Online Remote PowerShell
    
  - Windows Azure Active Directory módulo para Windows PowerShell para o acesso ao diretório acesso Office 365
    
Para a conta da Sala do Skype, o seguinte licenciamento é exigido:
  
- Um Skype para negócios Online plano 2 ou Office 365 E1 ou E3 licença é necessária para habilitar Skype reuniões.
    
- Para dão direito a sala com o recurso de Enterprise Voice para que a sala pode ser habilitada com um número de telefone, um Skype para negócios Online plano 2 com a nuvem complemento de PBX ou Office 365 E5 é necessária (1).
    
- A disponibilidade da qualificação de Conferência por PSTN em uma determinada reunião é determinada pela licença do organizador da reunião.
    
- Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque a conta deve ser configurada como uma conta de caixa postal de recursos. 
    
## <a name="provisioning-overview"></a>Visão geral do provisionamento

O diagrama a seguir fornece uma visão geral da conta do sistema de sala do Skype provisionamento fluxo no Office 365.
  
![Etapas de provisionamento do Sistemas de Sala do Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar uma nova sala de conferência 

Talvez você já tenha uma caixa de correio de sala de recurso no Exchange que fornece o recurso de agendamento, ou você pode criar uma caixa de correio de recurso pela primeira vez facilitar a implantação do sistema do Skype sala. Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário. A provisão on-line do Exchange e Skype seções de provisão de negócios oferecem diretrizes para ambos os tipos de contas. Por exemplo, digamos que você tem as seguintes duas salas e você gostaria de implantar o sistema de sala do Skype para ambos deles:
  
- Conta existente da caixa de correio do recurso: confrm1@contoso.onmicrosoft.com
    
- Nova conta da caixa de correio do recurso: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisionamento do Exchange Online  

Primeiro, se conecte ao Exchange Online PowerShell, seguindo as instruções no tópico, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para definir uma conta de caixa de correio de sala de recurso existente para o sistema de sala Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para criar uma nova conta de caixa de correio de recursos do Exchange para o sistema de sala Skype, execute os seguintes comandos no PowerShell do Exchange Online:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Os comandos anteriores configurar ou criar uma nova conta de caixa de correio de recurso Exchange para uso do sistema de sala Skype habilitando a conta.
  
Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio. Consulte as etapas de 3 a 6 sob Implantações locais da floresta única para obter mais detalhes.

## <a name="assigning-a-skype-for-business-online-license"></a>Atribuindo uma licença do Skype for Business Online 

Agora você pode atribuir um Skype para Business Online (plano 2) ou Skype licença Business Online (plano 3) usando o portal do Office 365 administrativo conforme descrito em [atribuir ou remover licenças para o Office 365 para empresas](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou em [Skype para o complemento de negócios licenciamento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Depois de atribuir uma licença para Skype para Business Online, você poderá fazer logon e validar se a conta está ativa usando qualquer Skype para o cliente de negócios.
  
## <a name="skype-for-business-online-provisioning"></a>Provisionamento do Skype for Business Online  

Depois de uma sala de recurso conta da caixa de correio foi criada e habilitada, conforme mostrado anteriormente, e a conta possui licenciado para Skype para Business Online da conta serão sincronizadas da floresta do Exchange Online com Skype para floresta Business Online usando o Floresta do Active Directory do Windows Azure. As etapas a seguir são necessárias para provisionar a conta de sistema do Skype sala no Skype para pool Business Online. Estas etapas são as mesmas para uma conta existente de caixa de correio de recurso ou de uma conta recém-criada (confrm1 ou confrm2), porque quando estiverem habilitados no Exchange Online, ambos dessas contas serão sincronizados com o Skype para Business Online da mesma maneira:
  
1. Crie uma sessão do PowerShell remoto. Observe que você precisará baixar Skype para negócios on-line do módulo do conector e o assistente Microsoft Online Services entrar e certifique-se de que o seu computador está configurado. Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar uma conta de sistema de sala Skype para Skype for Business, execute o seguinte comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Você pode obter o RegistrarPool retorna endereço onde sua Skype para usuários comerciais hospedados de uma de suas contas existentes usando o seguinte comando para essa propriedade:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Expiração da senha

No Office 365, a política de expiração de senha padrão para todas as contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente. Para contas de sistema do Skype sala, você pode selecionar a senha nunca expira configuração com as seguintes etapas.
  
1. Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário. 
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Definir a senha nunca expira configuração para a conta de sala do sistema de sala do Skype criada anteriormente usando o seguinte comando:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  

