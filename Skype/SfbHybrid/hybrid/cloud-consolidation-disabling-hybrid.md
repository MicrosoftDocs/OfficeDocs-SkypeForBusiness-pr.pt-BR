---
title: Desabilitar a migração híbrida para concluir a nuvem
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
localization_priority: Normal
description: Este artigo inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação de nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 36ec3cba2d821cc8554e0fba95108756c83b7b3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120350"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a>Desabilitar a migração híbrida para concluir a migração para a nuvem: Visão geral

Depois de mover todos os usuários do local para a nuvem, você poderá desativar a implantação do Skype for Business local. Além de remover qualquer hardware, uma etapa crítica é separar logicamente essa implantação local do Microsoft 365 ou do Office 365 desabilitando o híbrido. Para desabilitar a configuração híbrida, são necessárias três etapas:

1. Atualizar registros DNS para apontar para o Microsoft 365 ou Office 365.

2. Desabilite o espaço de endereço sip compartilhado (também conhecido como "domínio dividido") na organização do Microsoft 365 ou office 365.

3. Desabilite a capacidade no local de se comunicar com o Microsoft 365 ou o Office 365.

Essas etapas separam logicamente sua implantação local do Skype for Business Server do Office 365 e devem ser feitas juntas como uma unidade. Os detalhes de cada etapa são fornecidos neste artigo abaixo. Depois que isso for concluído, você poderá desmantelar sua Implantação local do Skype for Business usando um dos dois métodos referenciados abaixo.

> [!Important] 
>Depois que essa separação lógica for concluída, os atributos msRTCSIP do Active Directory local ainda terão valores e continuarão a sincronizar por meio do Azure AD Connect no Azure AD. Como você desativa o ambiente local depende se você pretende deixar esses atributos no lugar ou primeiro descompactá-los do Active Directory local. Esteja ciente de que limpar os atributos msRTCSIP locais depois que você tiver migrado do local pode resultar em perda de serviço para os usuários! Detalhes e trocas das duas abordagens de desativação são descritos mais adiante.

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a>Desabilitar a migração híbrida para concluir a migração para a nuvem: Etapas detalhadas

1. *Atualize o DNS para apontar para o Microsoft 365 ou Office 365.* O DNS externo da organização para a organização local precisa ser atualizado para que os registros do Skype for Business apontem para o Microsoft 365 ou o Office 365 em vez da implantação local. Especificamente:

    |Tipo de registro|Nome|TTL|Valor|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|

    Além disso, os registros CNAME para meet ou dialin (se presente) podem ser excluídos. Por fim, quaisquer registros DNS do Skype for Business em sua rede interna devem ser removidos.

    > [!Note] 
    > Em casos raros, a alteração do DNS de apontar para o Microsoft 365 ou Office 365 local para sua organização pode fazer com que a federação com algumas outras organizações pare de funcionar até que outra organização atualize sua configuração de federação:
    >
    > - Todas as organizações federadas que estão usando o modelo de Federação Direta mais antigo (também conhecido como Servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN de proxy. Esse modelo de federação herdado não se baseia nos registros SRV DNS, portanto, essa configuração ficará desa datada quando sua organização for para a nuvem.
    > 
    > - Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed.online.lync. <span> com precisará atualizar sua configuração para habilitar isso. Essa situação só será possível se a organização federada for puramente local e nunca tiver federado com qualquer locatário híbrido ou online. Nesse caso, a federação com essas organizações não funcionará até habilitar seu provedor de hospedagem.
    >
    > Se você suspeitar que qualquer um de seus parceiros federados possa estar usando Federação Direta ou não tiver federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso enquanto se prepara para concluir sua migração para a nuvem.


2.  *Desabilite o espaço de endereço sip compartilhado na organização do Microsoft 365 ou office 365.* O comando abaixo precisa ser feito a partir de uma janela do PowerShell do Skype for Business Online.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *Desabilite a capacidade no local de se comunicar com o Microsoft 365 ou o Office 365.* O comando abaixo precisa ser feito de uma janela local do PowerShell:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Gerenciando atributos após mover usuários do local para a nuvem

Por padrão, todos os usuários que foram habilitados anteriormente para o Skype for Business Server e posteriormente movidos para a nuvem ainda têm atributos msRTCSIP configurados no Active Directory local. Esses atributos, em particular endereço sip (msRTCSIP-PrimaryUserAddress) e potencialmente número de telefone (msRTCSIP-Line), continuam a sincronizar com o Azure AD. Se as alterações são necessárias para qualquer um dos atributos msRTCSIP, essas alterações devem ser feitas no Active Directory local e, em seguida, sincronizar com o Azure AD. No entanto, depois que a implantação do Skype for Business Server tiver sido removida, as ferramentas do Skype for Business Server não estarão disponíveis para gerenciar esses atributos.

Há duas opções disponíveis para lidar com essa situação:

1. Deixe os usuários habilitados para contas de servidor do Skype for Business como estão e gerencie os atributos msRTCSIP usando ferramentas do Active Directory. Isso garante nenhuma perda de serviço para usuários migrados e permite que você remova facilmente a implantação do Skype for Business Server eliminando (por exemplo, limpar) os servidores, sem um descomissionamento completo. No entanto, os usuários recém-licenciados não terão esses atributos preenchidos no Active Directory local e precisarão ser gerenciados online.

2.  Limpe todos os atributos msRTCSIP de usuários migrados no Active Directory local e gerencie esses atributos usando ferramentas online. Esse método permite uma abordagem de gerenciamento consistente para usuários existentes e novos, no entanto, pode resultar em uma perda temporária de serviço durante o processo de desativação local.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Método 1 - Gerenciar endereços sip e números de telefone para usuários no Active Directory

Os administradores podem gerenciar usuários que foram movidos anteriormente de um Skype for Business Server local para a nuvem, mesmo após a desativação da implantação local. Se você quiser fazer alterações no endereço sip de um usuário ou no número de telefone de um usuário (e o endereço sip ou número de telefone já tiver um valor no Active Directory local), você deve fazer isso no Active Directory local e permitir que os valores fluam para o Azure AD. Isso NÃO exige o Skype for Business Server local. Em vez disso, você pode modificar esses atributos diretamente no Active Directory local, usando o snap-in MMC de Usuários e Computadores do Active Directory (conforme mostrado abaixo) ou usando o PowerShell. Se você estiver usando o snap-in MMC, abra a página de propriedades do usuário, clique na guia Editor de Atributos e encontre os atributos apropriados para modificar:

- Para modificar o endereço sip de um usuário, modifique `msRTCSIP-PrimaryUserAddress` o . Observação, se o `ProxyAddresses` atributo contiver um endereço sip, atualize também esse valor como uma prática prática. Embora o endereço sip seja ignorado pelo O365 se estiver preenchido, ele pode ser usado por outros `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` componentes locais.

- Para modificar o número de telefone de um usuário, modifique `msRTCSIP-Line` *se ele já tiver um valor*.

  ![Ferramenta de computadores e usuários do Active Directory](../media/disable-hybrid-1.png)
  
-  Se o usuário não tiver originalmente um valor para o local antes da movimentação, você poderá modificar o número de telefone usando o parâmetro - no `msRTCSIP-Line` `onpremLineUri` [cmdlet Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) no módulo do PowerShell do Skype for Business Online.

Essas etapas não são necessárias para novos usuários criados após a desabilitação híbrida, e esses usuários podem ser gerenciados diretamente na nuvem. Se você estiver confortável usando a combinação desses métodos, bem como com a saída dos atributos msRTCSIP no seu Active Directory local, você pode simplesmente reimimá-los nos servidores locais do Skype for Business. No entanto, se você preferir limpar todos os atributos msRTCSIP e fazer uma desinstalação tradicional do Skype for Business Server, use o Método 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Método 2 - Limpar atributos do Skype for Business para todos os usuários locais no Active Directory

Essa opção requer esforço adicional e planejamento adequado, pois os usuários que foram movidos anteriormente de um Servidor do Skype for Business local para a nuvem são necessários para serem re provisionados. Esses usuários podem ser categorizados em duas categorias diferentes: usuários sem Sistema de Telefonia e usuários com Sistema de Telefonia. Os usuários com o Sistema de Telefonia terão uma perda temporária do serviço de telefonia como parte da transição do número de telefone de ser gerenciado no Active Directory local para a nuvem. **É recomendável executar um piloto envolvendo um pequeno número de usuários com o Sistema de Telefonia antes de iniciar operações de usuário em massa.** Para implantações grandes, os usuários podem ser processados em grupos menores em janelas de tempo diferentes. 

> [!NOTE]
> O processo é mais simples para usuários que têm um endereço sip correspondente e UserPrincipalName. Para organizações que têm usuários com valores não correspondentes nesses dois atributos, é necessário ter cuidado extra, conforme abaixo, para uma transição suave. 


1. Confirme se o seguinte cmdlet local do Skype for Business PowerShell retorna um resultado vazio. Um resultado vazio significa que nenhum usuário está no local e foi movido para o Office 365 ou desabilitado:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Grave o número de telefone atual dos usuários (LineUri), UserPrincipalName e informações relacionadas, executando o seguinte cmdlet local do Skype for Business Server PowerShell para exportar dados do usuário:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Antes de continuar SfbUserSettings.csv arquivo aberto e confirmar se todos os dados do usuário foram exportados com êxito. É recomendável manter uma cópia desse arquivo.  Não use esse arquivo nas etapas a seguir para processar usuários. 

3. Crie um arquivo com um grupo de usuários a ser usado nas etapas a seguir. Depois que o primeiro grupo de usuários for concluído com êxito, prossiga com o próximo grupo de usuários. No exemplo abaixo, os grupos de usuários são selecionados em ordem alfabética, mas você pode filtrar os usuários com base em critérios que corresponde a como você gostaria de processar os usuários.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Antes de continuar SfbUsers.csv arquivo aberto e confirmar que os dados do usuário foram exportados com êxito. Você precisará do LineUri (número de telefone), UserPrincipalName, SamAccountName e SipAddress desse arquivo em uma etapa posterior.

4. Exclua as informações de atributo relacionadas ao Skype for Business Server do Active Directory para o conjunto de usuários que você está pronto para atualizar.  Há duas etapas para esse processo, conforme mostrado abaixo.

   > [!Important] 
   > Após o próximo ciclo de Sincronização do AAD após executar esta etapa, os usuários com o Sistema de Telefonia que foram movidos anteriormente de um Skype for Business Server local para a nuvem perderão a capacidade de fazer e receber chamadas até que a etapa 8 seja concluída e confirmada com êxito na etapa 9. Além disso, certifique-se de ter salvo os números de telefone do usuário e as informações relacionadas conforme a etapa 2, já que essas informações são necessárias para essa etapa.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Em seguida, para o mesmo conjunto de usuários, desempacote o valor de msRTCSIP-DeploymentLocator usando o PowerShell local do Active Directory:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Execute o seguinte cmdlet local do Skype for Business PowerShell para adicionar o valor de endereço sip de volta ao proxy local do Active DirectoryAddresses. Isso impedirá problemas de interoperabilidade que dependem desse atributo. 

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

6. Executar a sincronização do Azure AD

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Aguarde o provisionamento do usuário ser concluído. Você pode monitorar o andamento do provisionamento do usuário executando o seguinte comando do PowerShell do Skype for Business Online. O seguinte comando do PowerShell do Skype for Business Online retorna um resultado vazio assim que o processo é concluído.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Execute o seguinte comando do PowerShell do Skype for Business Online para atribuir números de telefone e habilitar usuários para o Sistema de Telefonia:
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  Se você ainda tiver pontos de extremidade do Skype for Business (clientes Skype ou telefones de terceiros), também deseja definir -HostedVoiceMail como $true. Se sua organização estiver usando apenas pontos de extremidade do Teams para usuários habilitados para voz, essa configuração não será aplicável aos usuários. 

9. Confirme se os usuários com a funcionalidade do Sistema de Telefonia foram provisionados corretamente. O seguinte comando do PowerShell do Skype for Business Online retorna um resultado vazio assim que o processo é concluído.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. Repita as etapas de 3 a 9 até que todos os usuários sejam processados.

11. Confirme se todos os usuários foram processados com êxito executando os dois comandos do PowerShell a seguir.

    Comando local do PowerShell do Skype for Business Server local:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Comando do PowerShell do Skype for Business Online:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a>Confira também

[Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md)