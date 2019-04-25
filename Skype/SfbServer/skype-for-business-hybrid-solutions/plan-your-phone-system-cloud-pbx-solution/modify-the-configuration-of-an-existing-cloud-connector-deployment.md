---
title: Modificar a configuração de uma implantação do Cloud Connector existente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga as etapas deste tópico para modificar a configuração de um Skype existente para o conector de nuvem Business Edition 1.4.1 ou implantação posterior.
ms.openlocfilehash: abe7d9be6ec0ae48ff8cbac09475c6a41bf2a49f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237606"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificar a configuração de uma implantação do Cloud Connector existente
 
Siga as etapas deste tópico para modificar a configuração de um Skype existente para o conector de nuvem Business Edition 1.4.1 ou implantação posterior. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificar a configuração de um único site
<a name="BKMK_SIngleSite"> </a>

Se houver apenas um dispositivo no site, quando quiser alterar as definições de configuração depois que o dispositivo for implantado, você poderá modificar o arquivo CloudConnector.ini e iniciar a implantação novamente.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no servidor host:  
    
   ```
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para cancelar o registro do dispositivo:
    
   ```
   Unregister-CcAppliance
   ```

3. Atualize o arquivo CloudConnector.ini no Diretório de Dispositivos.
    
4. Execute o seguinte cmdlet para atualizar a configuração: (esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)
    
   ```
   Import-CcConfiguration 
   ```

5. Execute o seguinte cmdlet para registrar o dispositivo novamente:
    
   ```
   Register-CcAppliance
   ```

6. Execute o seguinte cmdlet para instalar o Skype for Business Cloud Connector Edition:
    
   ```
   Install-CcAppliance
   ```

Se houver mais de um dispositivo no site, você deverá seguir estas etapas, modificar o arquivo CloudConnector.ini e reimplantar os dispositivos um a um.
  
1. Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes do dispositivo atual.  
    
   ```
   Uninstall-CcAppliance
   ```

2. Execute o seguinte cmdlet para cancelar o registro do dispositivo:
    
   ```
   Unregister-CcAppliance
   ```

3. Atualize o arquivo CloudConnector.ini no Diretório de Dispositivos.
    
4. Execute o seguinte cmdlet para atualizar a configuração: (esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)
    
   ```
   Import-CcConfiguration 
   ```

5. Execute o seguinte cmdlet para registrar o dispositivo novamente:
    
   ```
   Register-CcAppliance
   ```

6. Execute o seguinte cmdlet em todos os outros dispositivos do site para selecionar a configuração mais recente:
    
   ```
   Publish-CcAppliance
   ```

7. Execute o seguinte cmdlet para reimplantar o conector de nuvem no appliance atual:
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificar a configuração de vários sites
<a name="BKMK_MultipleSites"> </a>

Para modificar a configuração de vários sites em uma implantação, siga as etapas de um único site, atualizando um site por vez.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modificar a configuração ou seu locatário do Office 365 para habilitar atualizações automáticas
<a name="BKMK_MultipleSites"> </a>

Para habilitar atualizações automáticas do sistema operacional e atualizações automáticas de Bits, você deve usar o Skype para a conta de administrador de locatário Business para gerenciamento on-line e usar o PowerShell remoto de inquilinos da seguinte maneira.
  
Se você desabilitou as atualizações automáticas do sistema operacional ou atualizações automáticas de Bits, seu host e a máquina virtual podem perder as atualizações importantes do Windows e o conector de nuvem não irá atualizar automaticamente para a nova versão. É altamente recomendável que você habilite as atualizações automáticas.
  
1. A propriedade EnableAutoUpdate do site deve ser definida como true (o valor padrão). Execute o seguinte cmdlet para garantir que EnableAutoUpdate seja definido como True:
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Crie a janela de tempo de atualização automática para o locatário.
    
    A janela de tempo pode ser diária, semanal e mensal. Todas as janelas de tempo precisam de uma hora de início e duração.
    
   - Para a janela de tempo diária, apenas a hora de início e a duração são necessárias.  
    
   - Para a janela de tempo semanal, são necessários os dias da semana. Pode ser um único dia ou vários dias.
    
   - Para a janela de tempo mensal, pode haver 2 tipos. A primeira maneira é especificar o dia do mês, que pode ser um único dia. A segunda maneira é especificar semanas do mês, junto com os dias da semana, que podem ser um item ou vários itens.
    
   - Cada locatário pode ter 20 janelas de tempo definidas. A janela de tempo padrão será criada para um novo locatário como janela de tempo padrão para atualização do sistema operacional e do Bits. Execute os seguintes cmdlets para definir a janela de tempo diária, semanal ou mensal:
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Atribuir janelas de tempo de atualização ao site.  
    
     As janelas de tempo de atualização do Bits e do sistema operacional são configuradas separadamente. É possível atribuir uma ou várias janelas de tempo a ambos. Cada janela de tempo pode ser atribuída a diferentes locais e finalidades (atualização do Bits e atualização do sistema operacional). Execute o seguinte cmdlet para definir a janela de tempo do site:  
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Atualizar as credenciais exclusivas de administrador do locatário 
<a name="BKMK_MultipleSites"> </a>

Alterações administrativas no inquilino do Office 365 para o conector de nuvem forem feitas a partir de uma conta com as permissões necessárias. Nas versões do conector de nuvem antes 2.0, essa conta é uma conta de administração de locatário global dedicado. Nas versões do conector de nuvem 2.0 e posteriores, essa conta pode ser uma conta do Office 365 com Skype para direitos de administrador de negócios.
  
Se suas credenciais de conta de administrador alterar no Office 365, você também precisará atualizar as credenciais armazenadas em cache localmente no conector de nuvem, executando o seguinte comando do PowerShell de administrador em cada dispositivo do conector de nuvem que tiver implantado:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Atualizar a senha do servidor host 
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável à versão 2.0 e versões posteriores do Cloud Connector. 
  
Todas as credenciais do conector de nuvem são armazenadas no seguinte arquivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Quando for alterada a senha do servidor host, você precisará atualizar as credenciais armazenadas localmente.
  
Para atualizar as credenciais armazenadas localmente no dispositivo do conector de nuvem, use os cmdlets [Get-CcCredential](get-cccredential.md) e [Set-CcCredential](set-cccredential.md) e siga estas etapas:
  
1. Execute os seguintes comandos para recuperar as senhas das quais você precisará mais tarde:  
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Altere a senha da sua conta no servidor host.
    
3. Reinicie o servidor host.
    
4. Exclua o arquivo a seguir: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Iniciar um console do PowerShell como administrador e execute "Register-CcAppliance-Local" digitem novamente as senhas seguindo a descrição. Certifique-se de inserir a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector.
    
Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas de DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:
  
1. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
2. Quando solicitada a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.
    
2. Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:
    
1. Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
2. Quando solicitada a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1.  
    
## <a name="update-the-password-for-the-cceservice-account"></a>Atualizar a senha para a conta CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Esta seção é aplicável a versão do conector de nuvem 2.0.1 e posterior. 
  
O serviço do conector de nuvem executa o serviço de gerenciamento de conector de nuvem. A conta de CceService é criada durante a implantação de edição do conector de nuvem e armazenada nos seguintes arquivos: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "e"% SystemDrive%\Programdata\Cloudconnector\credentials … CceService.xml".
  
Para garantir que todos os aparelhos podem acessar o compartilhamento do diretório de site, a senha para a conta de CceService deve ser o mesmo em todos os aparelhos implantados dentro do site. Considere o seguinte:
  
- Por padrão, a conta de CceService está configurada como "A senha nunca expira". Quando você atualiza a senha, a Microsoft recomenda manter essa configuração.
    
- Você deve atualizar a senha durante períodos de uso não sejam de pico e fora do windows de tempo de atualização automática para bits ou atualizações do Windows. Quando você atualiza a senha, o aparelho precisa ser esvaziadas e reiniciado, que leva algum tempo. Reiniciar o aparelho interromperá operações de atualização automática. 
    
- Quando você altera a senha da conta CceService, você precisará especificar todas as credenciais e atualizá-los no arquivo armazenado localmente. 
    
Para cada dispositivo que pertence ao mesmo site PSTN, você precisará especificar o seguinte: 
  
1. Execute os seguintes comandos para recuperar os nomes de conta e senhas que você usará posteriormente:
    
   ```
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

2. Execute o cmdlet Enter-CcUpdate para esvaziar o aparelho e movê-lo no modo de manutenção manual.
    
3. Atualize a senha da conta CceService no servidor host.
    
4. Reinicie o servidor host.
    
5. Execute o cmdlet Restore-CcCredentials para redigitar as senhas seguindo a descrição. 
    
    Certifique-se de que você insira a mesma senha que você inseriu antes para a implantação do conector de nuvem, exceto a conta CceService. Para a conta de CceService, insira sua nova senha. Certifique-se de que a nova senha para a conta de CceService é o mesmo para todos os aparelhos no site do PSTN.
    
6. Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas de DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:
    
7. Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:
    
   - Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
   - Quando solicitada a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.
    
8. Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:
    
   - Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.
    
   - Quando solicitada a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1.  
    
9. Execute o cmdlet sair-CcUpdate para mover o aparelho de modo de manutenção manual.
    
10. Após concluir essas etapas em todos os aparelhos no mesmo site PSTN, exclua os seguintes arquivos no diretório raiz do site:
    
    - CcLockFile
    
    - Site_\<fqdn do Pool de Sip externa de borda\>
    
    - Tenant_\<fqdn do Pool de Sip externa de borda\>
    
    - TenantConfigLock_\<fqdn do Pool de Sip externa de borda\>
    
## <a name="add-a-new-sip-domain"></a>Adicionar um novo domínio SIP 
<a name="BKMK_UpdatePassword"> </a>

Para adicionar um novo domínio SIP (ou vários domínios SIP) à sua implantação do conector de nuvem existente, faça o seguinte:
  
1. Verifique se você concluiu as etapas para atualizar seu domínio no Office 365 e se consegue adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Atualize o arquivo de configuração do conector de nuvem com o novo domínio SIP ou domínios.
    
3. Solicite um novo certificado de externa de borda com nomes de SAN adicionais para sip.domain para cada domínio SIP definido na sua configuração do conector de nuvem. 
    
4. Defina o caminho do certificado externo de Borda da seguinte maneira:
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Siga as instruções para [Modificar a configuração de um único site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [Modificar a configuração de vários sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificar o domínio SIP primário
<a name="BKMK_UpdatePassword"> </a>

Se você precisar alterar o domínio SIP primário em sua implantação do conector de nuvem, faça o seguinte:
  
1. Verifique se você concluiu as etapas para atualizar seu domínio no Office 365 e se consegue adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Atualize o arquivo de configuração do conector de nuvem com o novo domínio SIP.
    
3. Solicite um novo certificado de externa de borda com nomes de SAN adicionais para sip.domain para cada domínio SIP definido na sua configuração do conector de nuvem. 
    
4. Defina o caminho do certificado externo de Borda da seguinte maneira:
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Remova o registro de Inquilino de cada dispositivo em um site executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    Remova o registro do site de cada um dos sites executando o seguinte cmdlet no PowerShell do Skype for Business Online:
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Desinstale cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     Registre cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```
   Register-ccAppliance
   ```

9. 
    
     Instalar cada aparelho, um por um, executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Substitua o certificado de borda externa de um novo certificado
<a name="BKMK_UpdatePassword"> </a>

Quando você precisa substituir o certificado de borda externa em seus aparelhos de conector de nuvem, você precisará obter um novo certificado de borda, preparar o arquivo PFX que contém a chave privada e uma cadeia de certificados completo e, em seguida, faça o seguinte em cada dispositivo:
  
1. Coloque o aparelho no modo de manutenção usando o cmdlet Enter-CcUpdate.
    
2. Execute o seguinte comando: 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se a senha do novo certificado é o mesmo que o antigo, a importação será aprovada. Se a senha for diferente, você receberá um erro de que a senha é incorreta, e você deverá redefinir a senha, executando o cmdlet Register-CcAppliance com o parâmetro - Local, e, em seguida, repetindo a etapa 2. 
    
4. Levar o aparelho de modo de manutenção usando o cmdlet sair - CcUpdate.
    

