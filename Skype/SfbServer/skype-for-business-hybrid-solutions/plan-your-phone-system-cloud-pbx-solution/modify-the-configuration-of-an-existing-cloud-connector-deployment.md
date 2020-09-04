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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga as etapas neste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359107"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificar a configuração de uma implantação do Cloud Connector existente

> [!Important]
> O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online. Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Siga as etapas neste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar a configuração de um único site
<a name="BKMK_SIngleSite"> </a>

Se houver apenas um dispositivo no site, quando você quiser alterar as definições de configuração depois que o dispositivo for implantado, você poderá modificar o arquivo de CloudConnector.ini e iniciar a implantação novamente.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no servidor host: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para cancelar o registro do dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Atualize o arquivo de CloudConnector.ini no diretório de dispositivos.
    
4. Execute o seguinte cmdlet para atualizar a configuração: (esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Execute o seguinte cmdlet para registrar o dispositivo novamente:
    
   ```powershell
   Register-CcAppliance
   ```

6. Execute o cmdlet a seguir para instalar o Skype for Business Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Se houver mais de um dispositivo no site, você precisará seguir estas etapas, modificar o arquivo CloudConnector.ini e reimplantar os dispositivos um por um.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no dispositivo atual: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para cancelar o registro do dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Atualize o arquivo de CloudConnector.ini no diretório de dispositivos.
    
4. Execute o seguinte cmdlet para atualizar a configuração: (esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Execute o seguinte cmdlet para registrar o dispositivo novamente:
    
   ```powershell
   Register-CcAppliance
   ```

6. Execute o cmdlet a seguir em todos os outros dispositivos no site para selecionar a configuração mais recente:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Execute o seguinte cmdlet para reimplantar o Cloud Connector no dispositivo atual:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificar a configuração de vários sites
<a name="BKMK_MultipleSites"> </a>

Para modificar a configuração de vários sites em uma implantação, siga as etapas de um único site, atualizando um site de cada vez.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Modificar a configuração da sua organização do Microsoft 365 ou do Office 365 para habilitar atualizações automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar as atualizações automáticas do sistema operacional e as atualizações automáticas do bits, você deve usar a conta de administrador locatário do Skype for Business para gerenciamento online e usar o PowerShell remoto do locatário, da seguinte maneira.
  
Se você desabilitou as atualizações automáticas do sistema operacional ou as atualizações automáticas do bits, o host e a máquina virtual poderão perder atualizações importantes do Windows e o Cloud Connector não será atualizado para a nova versão automaticamente. É altamente recomendável que você habilite as atualizações automáticas.
  
1. A propriedade EnableAutoUpdate do site precisa ser definida como true (o valor padrão). Execute o cmdlet a seguir para certificar-se de que EnableAutoUpdate está definido como true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Crie a janela de tempo de atualização automática para o locatário.
    
    A janela de tempo pode ser diária, semanal e mensal. Todas as janelas de tempo precisam de um horário de início e uma duração.
    
   - Para uma janela de tempo diária, apenas a hora de início e a duração são necessárias. 
    
   - Para uma janela de tempo semanal, os dias da semana são necessários, que podem ser um único dia ou vários dias.
    
   - Para uma janela de tempo mensal, pode haver dois tipos. O primeiro tipo é especificar o dia do mês, que pode ser um único dia. O segundo tipo é especificar as semanas do mês, junto com os dias da semana, que podem ser um único item ou vários itens.
    
   - Cada locatário pode ter 20 janelas de tempo definidas. A janela de tempo padrão será criada para um novo locatário como a janela de tempo padrão para atualização do sistema operacional e atualização de bits. Execute os seguintes cmdlets para definir a janela de tempo diária, semanal ou mensal:
    
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
    
     O tempo de atualização do bits e as janelas de tempo de atualização de so são configurados separadamente. Ambas podem ser atribuídas a uma única ou várias janelas de tempo. Cada janela de tempo pode ser atribuída a diferentes sites e objetivos diferentes (atualização de bits e atualização de so). Execute o seguinte cmdlet para definir a janela de tempo do site: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Atualizar as credenciais de administrador de locatários dedicados
<a name="BKMK_MultipleSites"> </a>

Alterações administrativas na organização do Microsoft 365 ou do Office 365 para o Cloud Connector são feitas de uma conta com as permissões necessárias. Nas versões do Cloud Connector anteriores a 2,0, essa conta é uma conta de administrador de locatário global dedicado. Nas versões 2,0 e posteriores do Cloud Connector, essa conta pode ser uma conta do Microsoft 365 ou do Office 365 com direitos de administrador do Skype for Business.
  
Se as suas credenciais de conta de administrador forem alteradas no Microsoft 365 ou no Office 365, você também precisará atualizar as credenciais armazenadas em cache localmente no Cloud Connector executando o seguinte comando do PowerShell do administrador em cada dispositivo do Cloud Connector implantado:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Atualizar a senha do servidor host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável para o Cloud Connector versão 2,0 e posterior. 
  
Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ". Quando a senha no servidor host for alterada, será necessário atualizar as credenciais armazenadas localmente.
  
Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, use os cmdlets [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e siga estas etapas:
  
1. Execute os seguintes comandos para recuperar as senhas que você precisará mais tarde: 
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. Altere a senha da sua conta no servidor host.
    
3. Reinicie o servidor host.
    
4. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".
    
5. Inicie um console do PowerShell como administrador e execute "Register-CcAppliance-local" para reinserir as senhas após a descrição. Certifique-se de inserir a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector.
    
Por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService. Se as senhas DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:
  
1. Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:
    
1. Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.
    
2. Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin retornada na etapa 1.
    
2. Execute Set-CcCredential-AccountType VmAdmin da seguinte maneira:
    
1. Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.
    
2. Quando for solicitada a nova credencial da conta, insira a senha da senha do VmAdmin retornada na etapa 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Atualizar a senha da conta CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável ao Cloud Connector versão 2.0.1 e posterior. 
  
O serviço do Cloud Connector executa o serviço de gerenciamento do Cloud Connector. A conta CceService é criada durante a implantação do Cloud Connector Edition e armazenada nos seguintes arquivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML "e"% SystemDrive% \Programdata\Cloudconnector\credentials..CceService.xml ".
  
Para garantir que todos os dispositivos possam acessar o compartilhamento de diretório de site, a senha da conta CceService deve ser a mesma em todos os dispositivos implantados no site. Lembre-se do seguinte:
  
- Por padrão, a conta CceService é configurada como "a senha nunca expira". Ao atualizar a senha, a Microsoft recomenda manter essa configuração.
    
- Você deve atualizar a senha durante períodos de uso sem pico e fora das janelas de tempo de atualização automática para bits ou atualizações do Windows. Ao atualizar a senha, o dispositivo precisa ser esvaziado e reiniciado, o que leva algum tempo. Reiniciar o dispositivo interromperá as operações de atualização automática. 
    
- Ao alterar a senha da conta CceService, será necessário especificar todas as credenciais e atualizá-las no arquivo armazenado localmente. 
    
Para cada dispositivo que pertença ao mesmo site PSTN, será necessário especificar o seguinte: 
  
1. Execute os seguintes comandos para recuperar os nomes de conta e senhas que você usará posteriormente:
    
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

2. Execute o cmdlet Enter-CcUpdate para drenar o dispositivo e movê-lo para o modo de manutenção manual.
    
3. Atualize a senha da conta CceService no servidor host.
    
4. Reinicie o servidor host.
    
5. Execute o cmdlet Restore-CcCredentials para inserir novamente as senhas após a descrição. 
    
    Certifique-se de inserir a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector, exceto para a conta CceService. Para a conta CceService, insira sua nova senha. Certifique-se de que a nova senha da conta CceService seja a mesma para todos os dispositivos no site PSTN.
    
6. Por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService. Se as senhas DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:
    
7. Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:
    
   - Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.
    
   - Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin retornada na etapa 1.
    
8. Execute Set-CcCredential-AccountType VmAdmin da seguinte maneira:
    
   - Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.
    
   - Quando for solicitada a nova credencial da conta, insira a senha da senha do VmAdmin retornada na etapa 1. 
    
9. Execute o cmdlet Exit-CcUpdate para mover o dispositivo para fora do modo de manutenção manual.
    
10. Após concluir essas etapas em todos os dispositivos no mesmo site PSTN, exclua os seguintes arquivos no diretório raiz do site:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Adicionar um novo domínio SIP
<a name="BKMK_UpdatePassword"> </a>

Para adicionar um novo domínio SIP (ou vários domínios SIP) à sua implantação existente do Cloud Connector, faça o seguinte:
  
1. Verifique se você concluiu as etapas para atualizar seu domínio no Microsoft 365 ou no Office 365 e tem a capacidade de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou no Office 365, consulte [Adicionar um domínio ao microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Atualize o arquivo de configuração do Cloud Connector com o novo domínio ou domínios SIP.
    
3. Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do Cloud Connector. 
    
4. Defina o caminho para o novo certificado externo de borda da seguinte maneira:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Siga as instruções para [Modificar a configuração de um único site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [Modificar a configuração de vários sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificar o domínio SIP primário
<a name="BKMK_UpdatePassword"> </a>

Se você precisar alterar o domínio SIP primário em sua implantação do Cloud Connector, faça o seguinte:
  
1. Verifique se você concluiu as etapas para atualizar seu domínio no Microsoft 365 ou no Office 365 e tem a capacidade de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou no Office 365, consulte [Adicionar um domínio ao microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Atualize o arquivo de configuração do Cloud Connector com o novo domínio SIP.
    
3. Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do Cloud Connector. 
    
4. Defina o caminho para o novo certificado externo de borda da seguinte maneira:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Remova o registro do locatário para cada dispositivo em um site executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Remova o registro do site de cada site executando o seguinte cmdlet no PowerShell do Skype for Business Online:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Desinstale cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registre cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Instale cada um dos dispositivos, um a um, executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Substitua o certificado de borda externa por um novo certificado
<a name="BKMK_UpdatePassword"> </a>

Quando precisar substituir o certificado de borda externa em seus dispositivos do Cloud Connector, você precisará obter um novo certificado de borda, preparar o arquivo PFX contendo a chave privada e a cadeia de certificados completo e, em seguida, faça o seguinte em cada dispositivo:
  
1. Coloque o dispositivo no modo de manutenção usando o cmdlet Enter-CcUpdate.
    
2. Execute o seguinte comando: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se a senha do novo certificado for igual à antiga, a importação será bem-sucedida. Se a senha for diferente, você receberá um erro de que a senha está errada e será necessário redefinir a senha executando o cmdlet Register-CcAppliance com o parâmetro-local e, em seguida, repetindo a etapa 2. 
    
4. Retire o dispositivo do modo de manutenção, usando o cmdlet Exit-CcUpdate.
    

