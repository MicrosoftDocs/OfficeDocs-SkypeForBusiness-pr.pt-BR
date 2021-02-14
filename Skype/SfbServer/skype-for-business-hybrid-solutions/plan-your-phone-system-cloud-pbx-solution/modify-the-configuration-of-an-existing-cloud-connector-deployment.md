---
title: Modificar a configuração de uma implantação existente do Cloud Connector
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
description: Siga as etapas deste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359107"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificar a configuração de uma implantação existente do Cloud Connector

> [!Important]
> O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização atualizou para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Siga as etapas deste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar a configuração de um único site
<a name="BKMK_SIngleSite"> </a>

Se houver apenas um dispositivo no site, quando você quiser alterar as definições de configuração após a implantação do dispositivo, poderá modificar o arquivo CloudConnector.ini e iniciar a implantação novamente.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no servidor host: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para ressuitir o registro do dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Atualize o CloudConnector.ini no Diretório de Dispositivos.
    
4. Execute o seguinte cmdlet para atualizar a configuração: (Esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)
    
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

Se houver mais de um dispositivo no site, você precisará seguir estas etapas, modificar o arquivo CloudConnector.ini e reimplantar os dispositivos um a um.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no dispositivo atual: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para ressuitir o registro do dispositivo:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Atualize o CloudConnector.ini no Diretório de Dispositivos.
    
4. Execute o seguinte cmdlet para atualizar a configuração: (Esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Execute o seguinte cmdlet para registrar o dispositivo novamente:
    
   ```powershell
   Register-CcAppliance
   ```

6. Execute o seguinte cmdlet em todos os outros dispositivos do site para escolher a configuração mais recente:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Execute o seguinte cmdlet para reimplantar o Cloud Connector no dispositivo atual:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificar a configuração de vários sites
<a name="BKMK_MultipleSites"> </a>

Para modificar a configuração de vários sites em uma implantação, siga as etapas para um único site, atualizando um site por vez.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Modificar a configuração da sua organização do Microsoft 365 ou Office 365 para habilitar as atualizações automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar as atualizações automáticas do sistema operacional e as atualizações automáticas do Bits, você deve usar a conta de administrador de locatários do Skype for Business para gerenciamento online e usar o PowerShell remoto do locatário da seguinte forma.
  
Se você desabilitou as atualizações automáticas do sistema operacional ou as atualizações automáticas do Bits, o host e a máquina virtual podem perder atualizações importantes do Windows, e o Cloud Connector não atualizará para a nova versão automaticamente. É altamente recomendável que você habilita as atualizações automáticas.
  
1. A propriedade EnableAutoUpdate do site precisa ser definida como true (o valor padrão). Execute o seguinte cmdlet para garantir que EnableAutoUpdate seja definido como true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Crie uma janela de tempo de atualização automática para o locatário.
    
    A janela de tempo pode ser diária, semanal e mensal. Todas as janelas de tempo precisam de uma hora de início e uma duração.
    
   - Para uma janela de tempo diária, apenas a hora de início e a duração são necessárias. 
    
   - Para uma janela de tempo semanal, são necessários dias da semana, que podem ser um único dia ou vários dias.
    
   - Para uma janela de tempo mensal, pode haver dois tipos. O primeiro tipo é especificar o dia do mês, que pode ser um único dia. O segundo tipo é especificar as semanas do mês, juntamente com os dias da semana, que podem ser um único item ou vários itens.
    
   - Cada locatário pode ter janelas de 20 horas definidas. A janela de tempo padrão será criada para um novo locatário como a janela de tempo padrão para atualização do sistema operacional e atualização do Bits. Execute os cmdlets a seguir para definir a janela de tempo diária, semanal ou mensal:
    
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

   - Atribua janelas de tempo de atualização ao site. 
    
     O tempo de atualização do Bits e as janelas de tempo de atualização do sistema operacional são configurados separadamente. Ambos podem ser atribuídos a janelas de tempo única ou múltipla. Cada janela de tempo pode ser atribuída a diferentes sites e finalidades diferentes (atualização do Bits e atualização do sistema operacional). Execute o seguinte cmdlet para definir a janela de tempo do site: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Atualizar as credenciais de administrador de locatário dedicadas
<a name="BKMK_MultipleSites"> </a>

As alterações administrativas na organização do Microsoft 365 ou Office 365 para o Cloud Connector são feitas de uma conta com as permissões necessárias. Nas versões do Cloud Connector anteriores à 2.0, essa conta é uma conta de administrador de locatário global dedicada. Nas versões 2.0 e posteriores do Cloud Connector, essa conta pode ser uma conta do Microsoft 365 ou Office 365 com direitos de Administrador do Skype for Business.
  
Se as credenciais da sua conta de administrador mudarem no Microsoft 365 ou no Office 365, você também precisará atualizar as credenciais armazenadas em cache localmente no Cloud Connector executando o seguinte comando do Administrador do PowerShell em cada dispositivo do Cloud Connector implantado:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Atualizar a senha do servidor host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável ao Cloud Connector versão 2.0 e posterior. 
  
Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml". Quando a senha no servidor host for mudada, você precisará atualizar as credenciais armazenadas localmente.
  
Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, use os cmdlets [Get-CcCredential](get-cccredential.md) e [Set-CcCredential](set-cccredential.md) e siga estas etapas:
  
1. Execute os seguintes comandos para recuperar as senhas de que você precisará mais tarde: 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Altere a senha da sua conta no servidor host.
    
3. Reinicie o servidor host.
    
4. Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".
    
5. Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description. Certifique-se de inserir a mesma senha inserida anteriormente para a implantação do Cloud Connector.
    
Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas domainAdmin, VMAdmin e CceService retornadas na etapa 1 são diferentes, você deve executar as seguintes etapas:
  
1. Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:
    
1. Quando solicitado a inserir a credencial da conta antiga, insira a credencial usada para a senha do CceService.
    
2. Quando for solicitado a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.
    
2. Execute Set-CcCredential -AccountType VmAdmin da seguinte forma:
    
1. Quando solicitado a inserir a credencial da conta antiga, insira a credencial usada para a senha do CceService.
    
2. Quando for solicitado a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Atualizar a senha da conta CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável ao Cloud Connector versão 2.0.1 e posterior. 
  
O serviço Cloud Connector executa o serviço gerenciamento do Cloud Connector. A conta CceService é criada durante a implantação do Cloud Connector Edition e armazenada nos seguintes arquivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" e "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Para garantir que todos os dispositivos possam acessar o compartilhamento de diretório do site, a senha da conta CceService deve ser a mesma em todos os dispositivos implantados no site. Lembre-se do seguinte:
  
- Por padrão, a conta CceService é configurada como "A senha nunca expira". Quando você atualiza a senha, a Microsoft recomenda manter essa configuração.
    
- Você deve atualizar a senha durante períodos de uso fora de pico e fora das janelas de tempo de atualização automática para bits ou atualizações do Windows. Quando você atualiza a senha, o dispositivo precisa ser esvaziado e reiniciado, o que leva algum tempo. Reiniciar o dispositivo interromperá as operações de atualização automática. 
    
- Ao alterar a senha da conta CceService, você precisará especificar todas as credenciais e atualizá-las no arquivo armazenado localmente. 
    
Para cada dispositivo que pertence ao mesmo site PSTN, você precisará especificar o seguinte: 
  
1. Execute os seguintes comandos para recuperar os nomes de conta e senhas que você usará mais tarde:
    
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

2. Execute o Enter-CcUpdate cmdlet para esvaziar o dispositivo e movê-lo para o modo de manutenção manual.
    
3. Atualize a senha da conta CceService no servidor host.
    
4. Reinicie o servidor host.
    
5. Execute o Restore-CcCredentials cmdlet para inserir as senhas de acordo com a descrição. 
    
    Certifique-se de inserir a mesma senha inserida anteriormente para a implantação do Cloud Connector, exceto para a conta do CceService. Para a conta CceService, insira sua nova senha. Certifique-se de que a nova senha da conta CceService seja a mesma para todos os dispositivos no site PSTN.
    
6. Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas domainAdmin, VMAdmin e CceService retornadas na etapa 1 são diferentes, você deve executar as seguintes etapas:
    
7. Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:
    
   - Quando solicitado a inserir a credencial da conta antiga, insira a credencial usada para a senha do CceService.
    
   - Quando for solicitado a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.
    
8. Execute Set-CcCredential -AccountType VmAdmin da seguinte forma:
    
   - Quando solicitado a inserir a credencial da conta antiga, insira a credencial usada para a senha do CceService.
    
   - Quando for solicitado a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1. 
    
9. Execute o Exit-CcUpdate cmdlet para mover o dispositivo para fora do modo de manutenção manual.
    
10. Depois de concluir essas etapas em todos os dispositivos no mesmo site PSTN, exclua os seguintes arquivos no diretório raiz do site:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Adicionar um novo domínio SIP
<a name="BKMK_UpdatePassword"> </a>

Para adicionar um novo domínio SIP (ou vários domínios SIP) à sua implantação existente do Cloud Connector, faça o seguinte:
  
1. Certifique-se de ter concluído as etapas para atualizar seu domínio no Microsoft 365 ou Office 365 e ter a capacidade de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou Office 365, confira Adicionar um domínio ao [Microsoft 365 ou Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Atualize o arquivo de configuração do Cloud Connector com o novo domínio SIP ou domínios.
    
3. Solicite um novo certificado externo de Borda com nomes SAN adicionais para sip.domain para cada domínio SIP definido na configuração do Cloud Connector. 
    
4. De definir o caminho para o novo certificado externo de Borda da seguinte forma:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Siga as instruções para [modificar a configuração de um único site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou modificar a [configuração de vários sites.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Modificar o domínio SIP principal
<a name="BKMK_UpdatePassword"> </a>

Se você precisar alterar o domínio SIP principal em sua implantação do Cloud Connector, faça o seguinte:
  
1. Certifique-se de ter concluído as etapas para atualizar seu domínio no Microsoft 365 ou Office 365 e ter a capacidade de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou Office 365, confira Adicionar um domínio ao [Microsoft 365 ou Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Atualize o arquivo de configuração do Cloud Connector com o novo domínio SIP.
    
3. Solicite um novo certificado externo de Borda com nomes SAN adicionais para sip.domain para cada domínio SIP definido na configuração do Cloud Connector. 
    
4. De definir o caminho para o novo certificado externo de Borda da seguinte forma:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Remova o registro de locatário para cada dispositivo em um site executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Remova o registro do site para cada site executando o seguinte cmdlet no PowerShell do Skype for Business Online:
    
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
    
     Instale cada dispositivo, um a um, executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Substituir o certificado de Borda externo por um novo certificado
<a name="BKMK_UpdatePassword"> </a>

Quando você precisar substituir o certificado de Borda externo nos dispositivos do Cloud Connector, precisará obter um novo certificado de Borda, preparar o arquivo PFX que contém a chave privada e a cadeia de certificados completa e, em seguida, fazer o seguinte em cada dispositivo:
  
1. Coloque o dispositivo no modo de manutenção usando o Enter-CcUpdate cmdlet.
    
2. Execute o seguinte comando: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se a senha do novo certificado for a mesma do antigo, a importação será bem-sucedida. Se a senha for diferente, você receberá um erro de que a senha está errada e precisará redefinir a senha executando o cmdlet Register-CcAppliance com o parâmetro -Local e repetindo a etapa 2. 
    
4. Tire o dispositivo do modo de manutenção usando o cmdlet Exit -CcUpdate.
    

