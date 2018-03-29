---
title: Referência de cmdlet do Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: A tabela a seguir lista os cmdlets do Skype for Business Cloud Connector Edition com uma breve descrição e links para mais informações.
ms.openlocfilehash: 5528b7ef5d2fe0ccfab680f2300b444f0532a059
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="cloud-connector-cmdlet-reference"></a>Referência de cmdlet do Cloud Connector
 
A tabela a seguir lista os cmdlets do Skype for Business Cloud Connector Edition com uma breve descrição e links para mais informações.
  
> [!NOTE]
> Você deve executar todos os cmdlets no computador host do Cloud Connector e executar a sessão do PowerShell como Administrador. 
  
|**Nome do cmdlet**|**Descrição**|
|:-----|:-----|
|[CcCertificationAuthority de backup](backup-cccertificationauthority.md) <br/> Versão 1.4.2 e posteriores  <br/> |Faz backup do serviço de autoridade de certificação em um arquivo e salva na pasta AC no diretório de compartilhamento de site.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Cloud Connector.   <br/> |
|[Insira-CcUpdate](enter-ccupdate.md) <br/> |Prepara o servidor host do Cloud Connector para o processo de atualização colocando-o no modo de manutenção. O aparelho é "esvaziado;" ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas são rejeitadas.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Fecha o modo de manutenção de atualização no servidor host do Cloud Connector.    <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Exporta uma configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporta um arquivo de configuração de exemplo de conector de nuvem (. ini) para o diretório de aparelho de um aparelho de conector de nuvem. Você pode modificar e renomear o arquivo para usar na implantação.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versão 1.4.2 e posteriores  <br/> |Exporta o certificado de autoridade de certificação raiz para um arquivo local no servidor host do Cloud Connector.   <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera o diretório de trabalho no servidor host do Cloud Connector. Todos os arquivos de implantação são armazenados nesse diretório.    <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Mostra o diretório atual onde os logs para um aparelho de conector de nuvem são armazenados..  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versão 2.1 e posterior  <br/> |Fornece informações de diagnóstico para o aparelho de conector de nuvem.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Retorna a credencial da implantação do Cloud Connector existente.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Retorna o caminho do arquivo do certificado externo para a implantação do Cloud Connector. O usuário prepara esse certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Mostra o diretório atual em que os arquivos de configuração no nível do site são armazenados. A pasta contém os arquivos de instalação base do VHD e o conector de nuvem. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Mostra o diretório atual onde os logs de nível de site para o conector de nuvem são armazenados.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versão 2.0 e posteriores  <br/> |Retorna a versão na instância do Cloud Connector. A Get-CCVersion só pode ser usada no computador host do Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versão 2.0 e posteriores  <br/> |Importa o Skype para que a configuração do conector de nuvem Business Edition de um arquivo local para o servidor de host do conector de nuvem.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Instala o aparelho de conector de nuvem — incluindo o AD, máquinas virtuais do repositório de gerenciamento Central, o servidor de mediação e o servidor de borda — no servidor host.  <br/> |
|[Publicar-CcAppliance](publish-ccappliance.md) <br/> | Obtém informações de alta disponibilidade da configuração do inquilino online e publicá-lo para o aparelho de conector de nuvem no servidor host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra as informações do dispositivo para um site PSTN em uma configuração de locatário online. Um aparelho deve ser registrado antes que ele pode ser implantado e gerenciado pelo serviço de gerenciamento de conector de nuvem. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versão 1.4.2 e posteriores  <br/> |Remove o arquivo de backup do serviço de autoridade de certificação "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" na pasta CA sob o diretório de compartilhamento de sites para o conector de nuvem.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versão 1.4.2 e posteriores  <br/> |Remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.  <br/> |
|[Renovar-CcCACertificate](renew-cccacertificate.md) <br/> Somente a versão 1.4.2  <br/> |Reinstala o servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz:  <br/> |
|[Renovar-CcServerCertificate](renew-ccservercertificate.md) <br/> Somente a versão 1.4.2  <br/> |Renova os certificados para o Cloud Connector quando estão próximos de expirar ou já expiraram.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versão 1.4.2 e posteriores  <br/> |Redefine os servidores de autoridade de certificação para instalar um novo certificado de autoridade de certificação.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versão 2.1 e posterior  <br/> |Limpa as credenciais e solicita digitem novamente todas as credenciais usadas para a implantação atual do conector de nuvem.  <br/> |
|[CcLog de pesquisa](search-cclog.md) <br/> |Pesquisa os logs de chamada de entrada e saída no diretório de log de dispositivos do Cloud Connector.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Define a pasta de trabalho no servidor de host de conector de nuvem. Todos os arquivos de implantação são armazenados nesse diretório.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Define a credencial da implantação do Cloud Connector existente.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica o caminho onde o certificado para o Servidor de Mediação ou para o Servidor de Borda é armazenado.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Define o diretório onde os arquivos de configuração no nível do site do Cloud Connector serão armazenados. A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.  <br/> |
|[Iniciar-CcDownload](start-ccdownload.md) <br/> |Baixa os bits de conector de nuvem e o arquivo msi de maneira síncrona.  <br/> |
|[Iniciar-CcLogging](start-cclogging.md) <br/> |Gera o log de chamada de entrada e saída para um aparelho de conector de nuvem.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Log de chamadas de paradas de geração de entrada e saída para um aparelho de conector de nuvem.  <br/> |
|[Opção-CcVersion](switch-ccversion.md) <br/> |Desconecta o dispositivo em execução e alterna para um dispositivo recém-implantado ou de backup.    <br/> |
|[Desinstalar-CcAppliance](uninstall-ccappliance.md) <br/> |Desinstala o aparelho de nuvem conector a execução do servidor host.  <br/> |
|[Cancelar o registro de CcAppliance](unregister-ccappliance.md) <br/> |Cancela o registro do aparelho de conector de nuvem atual de um site PSTN na configuração do inquilino online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versão 2.0 e posteriores  <br/> |Reinstala o servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz:  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versão 2.0 e posteriores  <br/> |Renova os certificados para o Cloud Connector quando estão próximos de expirar ou já expiraram.  <br/> |
   

