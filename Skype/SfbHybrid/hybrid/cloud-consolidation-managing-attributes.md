---
title: Decidir como gerenciar os atributos após o encerramento
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: Este artigo descreve como gerenciar atributos depois de encerrar seu ambiente local.
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249013"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Decidir como gerenciar os atributos após o encerramento

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Por padrão, todos os usuários que foram habilitados para Skype for Business Server e depois movidos para a nuvem ainda têm atributos msRTCSIP configurados em seu Active Directory local. 

Esses atributos, em particular o endereço sip (msRTCSIP-PrimaryUserAddress) e o número de telefone (msRTCSIP-Line), continuam sincronizando com Azure AD. Se forem necessárias alterações em qualquer um dos atributos msRTCSIP, essas alterações deverão ser feitas no Active Directory local e sincronizar com Azure AD. No entanto, depois que a Skype for Business Server implantação for removida, as Skype for Business Server ferramentas de Skype for Business Server estarão disponíveis para gerenciar esses atributos.

Há duas opções disponíveis para lidar com essa situação:

1. Deixe os usuários habilitados para Skype for Business contas de servidor como estão e gerencie os atributos msRTCSIP usando ferramentas do Active Directory. Esse método não garante nenhuma perda de serviço para usuários migrados e permite remover a implantação do Skype for Business Server eliminando (por exemplo, apagar) os servidores, sem um encerramento completo. No entanto, os usuários recém-licenciados não terão esses atributos preenchidos em seu Active Directory local e precisarão ser gerenciados online.

2.  Limpe todos os atributos msRTCSIP de usuários migrados em seu Active Directory local e gerencie esses atributos usando ferramentas online. Esse método permite uma abordagem de gerenciamento consistente para usuários novos e existentes. No entanto, isso pode resultar em uma perda temporária de serviço durante o processo de encerramento local.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Método 1 – Gerenciar endereços sip e números de telefone para usuários no Active Directory

Os administradores podem gerenciar usuários que foram movidos de um Skype for Business Server local para a nuvem, mesmo após a desativação da implantação local. 

Se você quiser fazer alterações no endereço sip de um usuário ou no número de telefone de um usuário (e o endereço sip ou número de telefone já tiver um valor no Active Directory local), deverá fazer a alteração no Active Directory local e permitir que os valores fluam até Azure AD. Esse método NÃO requer Skype for Business Server. Em vez disso, você pode modificar esses atributos diretamente no Active Directory local, usando o snap-in Usuários e Computadores do Active Directory MMC (conforme mostrado abaixo) ou usando o PowerShell. Se você estiver usando o snap-in do MMC, abra a página de propriedades do usuário, clique na guia Editor de Atributos e localize os atributos apropriados para modificar:

- Para modificar o endereço sip de um usuário, modifique o `msRTCSIP-PrimaryUserAddress`.

    > [!NOTE]
    > Se o `ProxyAddresses` atributo contiver um endereço sip, atualize também esse valor como uma prática recomendada. Embora o endereço sip seja `ProxyAddresses` ignorado pelo O365 `msRTCSIP-PrimaryUserAddress` se for preenchido, ele poderá ser usado por outros componentes locais.

- Para modificar o número de telefone de um usuário, modifique `msRTCSIP-Line` *se ele já tiver um valor*.

  ![Ferramenta de computadores e usuários do Active Directory.](../media/disable-hybrid-1.png)


- `msRTCSIP-Line` Se o usuário não tiver originalmente um valor para o local antes da movimentação, `-PhoneNumber` você poderá modificar o número de telefone usando o parâmetro no [cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) no módulo Teams PowerShell.

Essas etapas não são necessárias para novos usuários criados depois que você desabilita o híbrido e esses usuários podem ser gerenciados diretamente na nuvem. Se você estiver familiarizado com o uso da combinação desses métodos e deixar os atributos msRTCSIP em vigor em seu Active Directory local, poderá fazer uma nova imagem dos servidores Skype for Business locais. No entanto, se você preferir limpar todos os atributos msRTCSIP e fazer uma desinstalação tradicional do Skype for Business Server, use o Método 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Método 2 – Limpar Skype for Business para todos os usuários locais no Active Directory

Essa opção requer mais esforço e planejamento adequado, pois os usuários que foram movidos de um Skype for Business Server local para a nuvem devem ser provisionados novamente. Esses usuários podem ser categorizados em duas categorias diferentes: usuários sem Sistema de Telefonia e usuários com Sistema de Telefonia. Os usuários com Sistema de Telefonia terão uma perda temporária de serviço de telefone como parte da transição do número de telefone de serem gerenciados Active Directory local para a nuvem. **É recomendável executar um piloto envolvendo um pequeno número de usuários com Sistema de Telefonia antes de iniciar operações de usuário em massa.** Para implantações grandes, os usuários podem ser processados em grupos menores em janelas de tempo diferentes. 

> [!NOTE] 
> Esse processo é mais simples para usuários que têm um endereço sip correspondente e UserPrincipalName. Para organizações que têm usuários com valores não correspondentes entre esses dois atributos, é necessário ter cuidado extra, conforme descrito abaixo, para uma transição suave.

> [!NOTE]
> Se você tiver configurado pontos de extremidade de aplicativo híbrido local para Atendedores Automáticos ou Filas de Chamadas, mova esses pontos de extremidade para o Microsoft 365 antes de encerrar Skype for Business Server. Para obter detalhes, [consulte Migrar pontos de extremidade de aplicativo híbrido antes de encerrar seu ambiente local](decommission-move-on-prem-endpoints.md).  


1. Confirme se o seguinte cmdlet Skype for Business PowerShell local retorna um resultado vazio. Um resultado vazio significa que nenhum usuário está hospedado no local e foi movido para Microsoft 365 ou foi desabilitado:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Registre o número atual de telefones dos usuários (LineUri), UserPrincipalName e informações relacionadas, executando o seguinte cmdlet local Skype for Business Server PowerShell para exportar dados do usuário:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Antes de continuar a SfbUserSettings.csv arquivo e confirmar se todos os dados do usuário foram exportados com êxito. É recomendável manter uma cópia desse arquivo.  Não use esse arquivo nas etapas a seguir para processar usuários. 

3. Crie um arquivo com um grupo de usuários a ser usado nas etapas a seguir. Depois que o primeiro grupo de usuários for concluído com êxito, prossiga com o próximo grupo de usuários. No exemplo abaixo, os grupos de usuários são selecionados em ordem alfabética. Você pode filtrar os usuários com base em critérios que correspondam a como você gostaria de processar os usuários.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Antes de continuar a SfbUsers.csv arquivo e confirmar se os dados do usuário foram exportados com êxito. Você precisará do LineUri (número de telefone), UserPrincipalName, SamAccountName e SipAddress desse arquivo em uma etapa posterior.

4. Exclua as informações de atributo relacionadas Skype for Business Server do Active Directory para o conjunto de usuários que você está pronto para atualizar.  Há duas etapas para esse processo, conforme mostrado abaixo.

   > [!Important] 
   > Após o próximo ciclo de AAD Sync após a execução desta etapa, os usuários com Sistema de Telefonia que foram movidos de um Skype for Business Server local para a nuvem perderão a capacidade de fazer e receber chamadas até que a etapa 8 seja concluída com êxito e confirmada na etapa 9. Além disso, verifique se você salvou os números de telefone do usuário e as informações relacionadas de acordo com a etapa 2, pois essas informações são necessárias para essa etapa.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Em seguida, para o mesmo conjunto de usuários, desmarque o valor de msRTCSIP-DeploymentLocator usando Active Directory local PowerShell:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Para adicionar o valor de endereço sip de volta ao Active Directory local proxyAddresses, execute o seguinte módulo Active Directory local para Windows PowerShell cmdlet. Essa ação impedirá problemas de interoperabilidade que dependem desse atributo. 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. Executar Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Aguarde a conclusão do provisionamento do usuário. Você pode monitorar o progresso do provisionamento de usuário executando o comando Teams PowerShell a seguir. O seguinte Teams comando do PowerShell retorna um resultado vazio assim que o processo é concluído.

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. Para atribuir números de telefone e habilitar usuários para Sistema de Telefonia, execute o seguinte comando Teams PowerShell:


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  Se você ainda tiver Skype for Business de extremidade (clientes Skype ou telefones de terceiros), também desejará definir -HostedVoiceMail como $true. Se sua organização estiver usando apenas Teams de extremidade para usuários habilitados para voz, essa configuração não será aplicável aos usuários. 

9. Confirme se os Sistema de Telefonia funcionalidade foram provisionados corretamente. O seguinte Teams comando do PowerShell retorna um resultado vazio assim que o processo é concluído.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. Repita as etapas de 3 a 9 até que todos os usuários sejam processados.

11. Confirme se todos os usuários foram processados com êxito executando os dois comandos do PowerShell a seguir.

    Comando do PowerShell Skype for Business Server local:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams comando do PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. Depois de concluir todas as etapas no Método 2, consulte Mover pontos de extremidade de aplicativo híbrido do local para [online](decommission-move-on-prem-endpoints.md) e remover o [Skype for Business Server](decommission-remove-on-prem.md) local para obter etapas adicionais para remover sua implantação Skype for Business Server local.


## <a name="see-also"></a>Confira também

- [Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)

- [Desativar o ambiente local do Skype for Business](decommission-on-prem-overview.md)

