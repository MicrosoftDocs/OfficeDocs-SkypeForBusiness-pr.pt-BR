---
title: Atribuir licenças do Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Saiba como atribuir licenças para recursos como audioconferências, o sistema telefônico, e planos de chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198733"
---
# <a name="assign-microsoft-teams-licenses"></a>Atribuir licenças Teams da Microsoft

Você pode atribuir licenças aos usuários recursos como conferência de áudio, sistema telefônico e planos de chamada. Este artigo explica como adicionar essas licenças em massa e para um usuário individual. 

> [!IMPORTANT]
> Consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obter informações sobre o que você precisará comprar de licenças e como comprá-los, dependendo do seu Office 365 planejar, portanto, os usuários têm a capacidade de chamar números de telefone fora da sua empresa, números para ligações gratuitas e conferência de áudio.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças

Aqui está o que você precisa saber antes de atribuir licenças de conferência de áudio, sistema telefônico e planejar a chamada.

- **Você está usando conectividade PSTN local para usuários híbridos?** Nesse caso, você precisará atribuir uma licença de sistema telefônico. Você não deve atribuir um plano de chamada.

- **Latência após a atribuição de licenças**: devido a latência entre o Office 365 e Teams da Microsoft, pode demorar até 24 horas para um usuário a ser atribuído um plano de chamar depois que você atribuir uma licença. Se após 24 horas, o usuário não for atribuído um plano de chamada, entre [em contato no suporte para produtos de negócios - ajuda de admin](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças. Se você precisar comprar mais licenças chamar planejar, escolha **comprar mais**.

- **Próximas etapas**: depois de atribuir licenças chamar planejar para seus usuários, você precisará obter seus números de telefone para sua organização e, em seguida, atribuir esses números para as pessoas na sua organização. Para obter instruções detalhadas, consulte [Configurar planos de chamada](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Atribuir uma licença de sistema telefônico e chamar planejar a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Atribuir licenças do sistema telefônico e chamar planejar em massa

1. Instale o Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW. Não tem o módulo instalado? Consulte [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.

2. Instale o Módulo do Windows Azure Active Directory. Não tem o módulo instalado? Consulte [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe do cmdlet.

3. Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

Este exemplo atribui uma licença Enterprise E3 junto com um Sistema de Telefonia e uma licença de Plano de Chamadas Domésticas.

O nome das licenças ou nomes de produto no script são listados em itálico (consulte o [sistema telefônico e planos de chamar os nomes dos produtos ou SKUs usados para execução de scripts](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), após o exemplo).

```
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nomes de produto do sistema telefônico e planos de chamar ou SKUs usados para execução de scripts

| Nome do produto | Nome de parte da SKU |
|--------------|---------------|
| Enterprise E5 (com Sistema de Telefonia) | ENTERPRISEPREMIUM |
| Enterprise E3 | ENTERPRISEPACK | 
| Enterprise E1 | STANDARDPACK | 
| Sistema Telefônico | MCOEV |
| Plano de chamadas internacionais do & domésticas | MCOPSTN2 |
| Planejar chamar domésticas (3000 minutos por usuário/mês para PR/US/CA, 1200 minutos por usuário/mês para países da UE) | MCOPSTN1 |
| Planejar chamar domésticas (120 minutos por usuário/mês para cada país) </br>*Observação: este plano não está disponível nos EUA*. | MCOPSTN5 |
| Planejar chamar domésticas (240 minutos por usuário/mês para cada país) </br>*Observação: este plano não está disponível nos EUA*. | MCOPSTN6 |
| Créditos de Comunicação | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Conferência de áudio: dicas e scripts para atribuir licenças

Aqui está o que você precisa saber antes de atribuir licenças de conferência de áudio.

- **Provedor de serviços de audioconferência de terceiros**: se alguém já estiver configurado para usar um provedor de serviços de audioconferência de terceiros, quando você atribuir uma licença de serviços de audioconferência, eles serão alterados para usar o Microsoft como um provedor de serviços de audioconferência. Você poderá mudá-lo de volta para o provedor terceirizado.

- **Próximas etapas**: depois de atribuir licenças de serviços de audioconferência, você precisa atribuir a um provedor de serviços de audioconferência. Consulte [Atribuir Microsoft como um provedor de serviços de audioconferência](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Atribuir uma licença de conferência de áudio a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Atribuir licenças de conferência de áudio em massa

1. Baixe e instale o [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Baixe e instale o Módulo Microsoft Azure Active Directory. Consulte [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe do cmdlet.

Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

O nome das licenças ou nomes de produto no script são listados em itálico. Consulte [nomes de produto de conferência de áudio ou SKUS usados para o script](#audio-conferencing-product-names-or-skus-used-for-scripting) de todos os nomes dos produtos.

Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService
#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nomes de produto de conferência áudio ou SKUS usados para execução de scripts

| Nome do produto | Nome de parte da SKU |
|--------------|---------------|
| Serviços de audioconferência (assinatura) | MCOMEETADV | 
| Áudio conferência pagar por minuto (pré-pago)</br>*Observação: requer créditos de comunicações para ser configurado e ativado*. | MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (sem Audioconferência) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (com serviços de audioconferência) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Créditos de Comunicação

Aqui está o que você precisa saber antes de atribuir licenças créditos de comunicações.

- **Os clientes corporativos E5**: mesmo se os usuários recebem licenças E5 da empresa, ainda recomendamos que você atribuir-lhes Communications créditos licenças.

- **Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários. Para obter instruções detalhadas, consulte [Configurar planos de chamada](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Atribuir uma licença de créditos de comunicação a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Atribuir licenças créditos de comunicações em massa

Dê uma olhada o script de exemplo para atribuir licenças de conferência de áudio. Atualizá-lo com as informações para atribuir licenças créditos de comunicações.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar Planos de Chamadas](set-up-calling-plans.md)
</br>
[Adicionar fundos e gerenciar Créditos de Comunicação](add-funds-and-manage-communications-credits.md)
