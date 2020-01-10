---
title: Modificar a configuração de uma implantação do Cloud Connector existente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga as etapas deste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior.
ms.openlocfilehash: ead952c0ba567a8e5d81c52144de597e50d24014
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002281"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificar a configuração de uma implantação do Cloud Connector existente
 
Siga as etapas deste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar a configuração de um único site
<a name="BKMK_SIngleSite"> </a>

Se houver apenas um dispositivo no site, quando quiser alterar as definições de configuração depois que o dispositivo for implantado, você poderá modificar o arquivo CloudConnector.ini e iniciar a implantação novamente.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no servidor host:  
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para cancelar o registro do dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Atualize o arquivo CloudConnector.ini no Diretório de Dispositivos.
    
4. Execute o cmdlet a seguir para atualizar a configuração: (esta etapa só se aplica à versão 2; para versões anteriores, pule para a próxima etapa.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Execute o seguinte cmdlet para registrar o dispositivo novamente:
    
   ```powershell
   Register-CcAppliance
   ```

6. Execute o seguinte cmdlet para instalar o Skype for Business Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Se houver mais de um dispositivo no site, você deverá seguir estas etapas, modificar o arquivo CloudConnector.ini e reimplantar os dispositivos um a um.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes do dispositivo atual.  
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para cancelar o registro do dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Atualize o arquivo CloudConnector.ini no Diretório de Dispositivos.
    
4. Execute o cmdlet a seguir para atualizar a configuração: (esta etapa só se aplica à versão 2; para versões anteriores, pule para a próxima etapa.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Execute o seguinte cmdlet para registrar o dispositivo novamente:
    
   ```powershell
   Register-CcAppliance
   ```

6. Execute o seguinte cmdlet em todos os outros dispositivos do site para selecionar a configuração mais recente:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Execute o cmdlet a seguir para reimplantar o conector de nuvem no dispositivo atual:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificar a configuração de vários sites
<a name="BKMK_MultipleSites"> </a>

Para modificar a configuração de vários sites em uma implantação, siga as etapas para um único site, atualizar um site de cada vez.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modificar a configuração ou seu locatário do Office 365 para habilitar atualizações automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar as atualizações automáticas do sistema operacional e as atualizações automáticas do bits, você deve usar a conta de administrador locatário do Skype for Business para gerenciamento online e usar o PowerShell remoto do locatário da seguinte maneira.
  
Se você desabilitou as atualizações automáticas do sistema operacional ou as atualizações automáticas do bits, o host e a máquina virtual podem perder atualizações importantes do Windows e o Cloud Connector não será atualizado para a nova versão automaticamente. É altamente recomendável que você habilite as atualizações automáticas.
  
1. A propriedade EnableAutoUpdate do site precisa ser definida como true (o valor padrão). Execute o seguinte cmdlet para garantir que EnableAutoUpdate seja definido como True:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Crie a janela de tempo de atualização automática para o locatário.
    
    A janela de tempo pode ser diária, semanal e mensal. Todas as janelas de tempo precisam de uma hora de início e duração.
    
   - Para a janela de tempo diária, apenas a hora de início e a duração são necessárias.  
    
   - Para a janela de tempo semanal, são necessários os dias da semana. Pode ser um único dia ou vários dias.
    
   - Para a janela de tempo mensal, pode haver 2 tipos. A primeira maneira é especificar o dia do mês, que pode ser um único dia. A segunda maneira é especificar semanas do mês, junto com os dias da semana, que podem ser um item ou vários itens.
    
   - Cada locatário pode ter 20 janelas de tempo definidas. A janela de tempo padrão será criada para um novo locatário como janela de tempo padrão para atualização do sistema operacional e do Bits. Execute os seguintes cmdlets para definir a janela de tempo diária, semanal ou mensal:
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Atribuir janelas de tempo de atualização ao site.  
    
     As janelas de tempo de atualização do Bits e do sistema operacional são configuradas separadamente. É possível atribuir uma ou várias janelas de tempo a ambos. Cada janela de tempo pode ser atribuída a diferentes locais e finalidades (atualização do Bits e atualização do sistema operacional). Execute o seguinte cmdlet para definir a janela de tempo do site:  
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Atualizar as credenciais exclusivas de administrador do locatário 
<a name="BKMK_MultipleSites"> </a>

Alterações administrativas no locatário do Office 365 para o Cloud Connector são feitas a partir de uma conta com as permissões necessárias. Em versões do conector de nuvem anteriores ao 2,0, essa conta é uma conta de administrador de locatário global dedicada. Nas versões do conector de nuvem 2,0 e posteriores, essa conta pode ser uma conta do Office 365 com direitos de administrador do Skype for Business.
  
Se as credenciais da sua conta de administrador forem alteradas no Office 365, você também precisará atualizar as credenciais armazenadas em cache localmente no conector de nuvem executando o seguinte comando do PowerShell do administrador em cada dispositivo de conexão de nuvem que você implantou:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Atualizar a senha do servidor host 
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável à versão 2.0 e versões posteriores do Cloud Connector. 
  
Todas as credenciais do conector de nuvem são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Quando for alterada a senha do servidor host, você precisará atualizar as credenciais armazenadas localmente.
  
Para atualizar as credenciais armazenadas localmente no dispositivo do conector de nuvem, use os cmdlets [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e siga estas etapas:
  
1. Execute os seguintes comandos para recuperar as senhas das quais você precisará mais tarde:  
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Altere a senha da sua conta no servidor host.
    
3. Reinicie o servidor host.
    
4. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Inicie um console do PowerShell como administrador e, em seguida, execute "Register-CcAppliance-local" para inserir novamente as senhas após a descrição. Certifique-se de inserir a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector.
    
Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas de DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:
  
1. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
2. Quando solicitada a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.
    
2. Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:
    
1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
2. Quando solicitada a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1.  
    
## <a name="update-the-password-for-the-cceservice-account"></a>Atualizar a senha da conta do CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável para o Cloud Connector versão 2.0.1 e posterior. 
  
O serviço do conector de nuvem executa o serviço de gerenciamento do Cloud Connector. A conta CceService é criada durante a implantação da edição do Cloud Connector e armazenada nos seguintes arquivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "e"%systemdrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".
  
Para garantir que todos os aparelhos possam acessar o compartilhamento de diretório de sites, a senha da conta CceService deve ser a mesma em todos os aparelhos implantados no site. Considere o seguinte:
  
- Por padrão, a conta CceService está configurada como "a senha nunca expira". Quando você atualiza a senha, a Microsoft recomenda manter essa configuração.
    
- Você deve atualizar a senha durante períodos de uso sem pico e fora das janelas de tempo de atualização automática para bits ou atualizações do Windows. Quando você atualiza a senha, o aparelho precisa ser descarregada e reiniciada, o que leva algum tempo. Reiniciar o aparelho irá interromper as operações de atualização automática. 
    
- Quando você alterar a senha da conta do CceService, será necessário especificar todas as credenciais e atualizá-las no arquivo armazenado localmente. 
    
Para cada dispositivo que pertence ao mesmo site PSTN, será preciso especificar o seguinte: 
  
1. Execute os seguintes comandos para recuperar os nomes de conta e as senhas que você usará mais tarde:
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. Execute o cmdlet Enter-CcUpdate para dissipar o aparelho e mova-o para o modo de manutenção manual.
    
3. Atualize a senha da conta do CceService no servidor host.
    
4. Reinicie o servidor host.
    
5. Execute o cmdlet Restore-CcCredentials para inserir novamente as senhas após a descrição. 
    
    Certifique-se de digitar a mesma senha que você inseriu antes para a implantação do conector de nuvem, exceto para a conta do CceService. Para a conta CceService, insira sua nova senha. Certifique-se de que a nova senha da conta CceService é a mesma para todos os aparelhos no site PSTN.
    
6. Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas de DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:
    
7. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
   - Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
   - Quando solicitada a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.
    
8. Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:
    
   - Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
   - Quando solicitada a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1.  
    
9. Execute o cmdlet Exit-CcUpdate para mover o aplicativo para fora do modo de manutenção manual.
    
10. Depois de concluir essas etapas em todos os aparelhos no mesmo site PSTN, exclua os seguintes arquivos no diretório raiz do site:
    
    - CcLockFile
    
    - Site_\<o FQDN do pool de conector SIP externo\>
    
    - Tenant_\<o FQDN do pool de conector SIP externo\>
    
    - TenantConfigLock_\<o FQDN do pool de conector SIP externo\>
    
## <a name="add-a-new-sip-domain"></a>Adicionar um novo domínio SIP 
<a name="BKMK_UpdatePassword"> </a>

Para adicionar um novo domínio SIP (ou vários domínios SIP) à sua implantação do conector de nuvem existente, faça o seguinte:
  
1. Verifique se você concluiu as etapas para atualizar seu domínio no Office 365 e se consegue adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Atualize o arquivo de configuração do conector de nuvem com o novo domínio SIP ou domínios.
    
3. Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do seu conector de nuvem. 
    
4. Defina o caminho do certificado externo de Borda da seguinte maneira:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Siga as instruções para [Modificar a configuração de um único site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [Modificar a configuração de vários sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificar o domínio SIP primário
<a name="BKMK_UpdatePassword"> </a>

Se você precisar alterar o domínio SIP primário em sua implantação do conector de nuvem, faça o seguinte:
  
1. Verifique se você concluiu as etapas para atualizar seu domínio no Office 365 e se consegue adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Atualize o arquivo de configuração do conector de nuvem com o novo domínio SIP.
    
3. Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do seu conector de nuvem. 
    
4. Defina o caminho do certificado externo de Borda da seguinte maneira:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Remova o registro do locatário para cada aplicativo em um site executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Remova o registro do site de cada um dos sites executando o seguinte cmdlet no PowerShell do Skype for Business Online:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Desinstale cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registre cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Instale cada utilitário, um por um, executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Substituir o certificado de borda externa por um novo certificado
<a name="BKMK_UpdatePassword"> </a>

Quando você precisar substituir o certificado de borda externa em seus aparelhos de conector de nuvem, será necessário obter um novo certificado de borda, preparar o arquivo PFX contendo a chave privada e a cadeia de certificados completo e, em seguida, fazer o seguinte em cada dispositivo:
  
1. Coloque o aparelho no modo de manutenção usando o cmdlet Enter-CcUpdate.
    
2. Execute o seguinte comando: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se a senha do novo certificado for igual à antiga, a importação será bem-sucedida. Se a senha for diferente, você receberá um erro informando que a senha está errada e será necessário redefinir a senha executando o cmdlet Register-CcAppliance com o parâmetro-local e, em seguida, repetindo a etapa 2. 
    
4. Retire o aparelho do modo de manutenção usando o cmdlet Exit-CcUpdate.
    

