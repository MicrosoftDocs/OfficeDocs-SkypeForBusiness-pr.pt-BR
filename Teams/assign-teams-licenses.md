---
title: Atribuir licenças do Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Saiba como atribuir licenças para recursos como conferência de áudio, sistema telefônico e planos de chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d51e2cf8a563c5094da923949c8e736aceeb864
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241878"
---
# <a name="assign-microsoft-teams-licenses"></a>Atribuir licenças do Microsoft Teams

Você pode atribuir licenças aos usuários para obter recursos como conferência de áudio, sistema telefônico e planos de chamada. Este artigo explica como adicionar essas licenças em massa e para um usuário individual. 

> [!IMPORTANT]
> Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obter informações sobre quais licenças você precisa comprar e como comprá-las, dependendo do seu plano do Office 365, para que os usuários recebam conferências de áudio, números de chamada gratuita e a capacidade de fazer chamadas para números de telefone de fora da sua empresa.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças

Veja aqui o que você precisa saber antes de atribuir licenças de conferência de áudio, sistema telefônico e plano de chamadas.

- **Você está usando conectividade PSTN local para usuários híbridos?** Em caso afirmativo, você só precisa atribuir uma licença do sistema telefônico. Você não deve atribuir um plano de chamada.

- **Latência após a atribuição de licenças**: devido à latência entre o Office 365 e o Microsoft Teams, pode levar até 24 horas para que um usuário receba um plano de chamada após a atribuição de uma licença. Se após 24 horas, o usuário não estiver atribuído a um plano de chamadas, [entre em contato com o suporte para produtos empresariais-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças. Se precisar comprar mais licenças do plano de chamadas, escolha **comprar mais**.

- **Próximas etapas**: após atribuir licenças de plano de chamada aos seus usuários, você precisará obter seus números de telefone para a sua organização e atribuir esses números às pessoas de sua organização. Para obter instruções passo a passo, consulte [configurar planos de chamada](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Atribuir uma licença do sistema telefônico e do plano de chamada a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Atribuir licenças do sistema telefônico e do plano de chamada em massa

1. Instale o Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW. Não tem o módulo instalado? Consulte [Assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para fazer o download.

2. Instale o Módulo do Windows Azure Active Directory. Não tem o módulo instalado? Consulte [gerenciar o Azure ad usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe de cmdlet.

3. Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

Este exemplo atribui uma licença Enterprise E3 junto com um Sistema de Telefonia e uma licença de Plano de Chamadas Domésticas.

O nome das licenças ou nomes de produto no script são listados em itálico (consulte o [sistema telefônico e os planos de chamada e os nomes de produto ou SKUs usados para script](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), após o exemplo).

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Nomes de produtos ou SKUs dos planos de chamadas e sistema telefônico usados para scripts

| Nome do produto | Nome de parte da SKU |
|--------------|---------------|
| Enterprise E5 (com Sistema de Telefonia) | ENTERPRISEPREMIUM |
| Enterprise E3 | ENTERPRISEPACK | 
| Enterprise E1 | STANDARDPACK | 
| Sistema Telefônico | MCOEV |
| Plano de chamadas internacionais & domésticas | MCOPSTN2 |
| Plano de chamadas domésticas (3000 minutos por usuário/mês para EUA/PR/CA, 1200 minutos por usuário/mês para países da UE) | MCOPSTN1 |
| Plano de chamadas domésticas (120 minutos por usuário/mês para cada país) </br>*Observação: este plano não está disponível para nós*. | MCOPSTN5 |
| Plano de chamadas domésticas (240 minutos por usuário/mês para cada país) </br>*Observação: este plano não está disponível para nós*. | MCOPSTN6 |
| Créditos de Comunicação | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Conferência de áudio: dicas e scripts para atribuir licenças

Veja o que você precisa saber antes de atribuir licenças de conferência de áudio.

- **Provedor de**serviços de audioconferência terceirizado: se alguém já estiver configurado para usar um provedor de serviços de audioconferência de terceiros, ao atribuir uma licença de audioconferência, ele será alterado para usar a Microsoft como provedor de serviços de audioconferência. Você poderá mudá-lo de volta para o provedor terceirizado.

- **Próximas etapas**: depois de atribuir licenças de audioconferência, você precisa atribuir um provedor de serviços de audioconferência. Consulte [atribuir a Microsoft como o provedor de áudio de audioconferência](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Atribuir uma licença de audioconferência a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Atribuir licenças de conferência de áudio em massa

1. Baixe e instale [o assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Baixe e instale o Módulo Microsoft Azure Active Directory. Consulte [gerenciar o Azure ad usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe de cmdlet.

Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:

O nome das licenças ou nomes de produtos no script são listados em itálico. Consulte os [nomes de produtos ou SKUs da conferência de áudio](#audio-conferencing-product-names-or-skus-used-for-scripting) para todos os nomes dos produtos.

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Nomes de produtos ou SKUS da conferência de áudio usados para scripts

| Nome do produto | Nome de parte da SKU |
|--------------|---------------|
| Conferência de áudio (assinatura) | MCOMEETADV | 
| Áudio conferência paga por minuto (pré-pago)</br>*Observação: exige que os créditos de comunicações sejam configurados e habilitados*. | MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (sem Audioconferência) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (com conferência de áudio) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Créditos de Comunicação

Veja o que você precisa saber antes de atribuir licenças de créditos de comunicações.

- **Clientes Enterprise E5**: mesmo que seus usuários tenham licenças Enterprise E5 atribuídas, ainda recomendamos que você atribua licenças de créditos de comunicações.

- **Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários. Para obter instruções passo a passo, consulte [configurar planos de chamada](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Atribuir uma licença de créditos de comunicações a um usuário

As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Atribuir licenças de créditos de comunicações em massa

Dê uma olhada no exemplo de script para atribuir licenças de audioconferência. Atualize-o com as informações para atribuir licenças de créditos de comunicações.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar Planos de Chamadas](set-up-calling-plans.md)
</br>
[Adicionar fundos e gerenciar Créditos de Comunicação](add-funds-and-manage-communications-credits.md)
