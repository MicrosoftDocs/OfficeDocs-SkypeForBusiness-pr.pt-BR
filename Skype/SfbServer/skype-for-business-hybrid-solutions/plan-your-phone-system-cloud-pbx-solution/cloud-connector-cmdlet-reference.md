---
title: Referência de cmdlet do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: A tabela a seguir lista os cmdlets do Skype for Business Cloud Connector Edition com uma breve descrição e links para mais informações.
ms.openlocfilehash: 58fed82857138bf9716db88648344e9140b29d6f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294374"
---
# <a name="cloud-connector-cmdlet-reference"></a>Referência de cmdlet do Cloud Connector
 
A tabela a seguir lista os cmdlets do Skype for Business Cloud Connector Edition com uma breve descrição e links para mais informações.
  
> [!NOTE]
> Você deve executar todos os cmdlets na máquina host do conector da nuvem, e você deve executar a sessão do PowerShell como administrador. 
  
|**Nome do cmdlet**|**Descrição**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versão 1.4.2 e posteriores  <br/> |Faz backup do serviço de autoridade de certificação em um arquivo e salva na pasta AC no diretório de compartilhamento de site.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Cria um arquivo VHDX (disco rígido virtual) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Cloud Connector.   <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara o servidor host do conector de nuvem para o processo de atualização, colocando-o no modo de manutenção. O aparelho está "esgotado"; ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas serão recusadas.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Sai do modo de manutenção de atualização no servidor host do conector da nuvem.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Exporta uma configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporta um arquivo de configuração de exemplo de conector de nuvem (. ini) para o diretório de aplicativos de um aparelho de conector de nuvem. Você pode modificar e renomear o arquivo a ser usado em sua implantação.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versão 1.4.2 e posteriores   <br/> |Exporta o certificado da CA raiz para um arquivo local no servidor host do conector da nuvem.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera o diretório de trabalho no servidor host do conector da nuvem. Todos os arquivos de implantação são armazenados nesse diretório.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Mostra o diretório atual em que os logs para um aparelho de conector de nuvem são armazenados.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versão 2,1 e posterior  <br/> |Fornece informações de diagnóstico para o dispositivo do conector de nuvem.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Retorna a credencial da implantação do conector de nuvem atual.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Retorna o caminho do arquivo de certificado externo para a implantação do conector de nuvem. O usuário prepara esse certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Mostra o diretório atual em que os arquivos de configuração no nível do site são armazenados. A pasta contém os arquivos de instalação do VHD e do conector de nuvem base. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do conector de nuvem.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Mostra o diretório atual onde os logs do conector de nuvem no nível do site estão armazenados.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versão 2.0 e posterior  <br/> |Retorna a versão na instância do Cloud Connector. A Get-CCVersion só pode ser usada no computador host do Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versão 2.0 e posterior  <br/> |Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do conector da nuvem.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Instala o dispositivo do conector de nuvem, incluindo o anúncio, o repositório de gerenciamento central, o servidor de mediação e as máquinas virtuais do servidor de borda, no servidor host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtém informações de alta disponibilidade da configuração do locatário online e a publica no dispositivo do conector de nuvem no servidor host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra as informações do dispositivo em um local de PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes de poder ser implantado e gerenciado pelo serviço de gerenciamento do conector de nuvem. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versão 1.4.2 e posteriores  <br/> |Remove o arquivo de backup do serviço de\<autoridade\>de certificação "SiteRootDirectory \CA\SfB CCE root. p12" na pasta CA sob o diretório de compartilhamento do site para o conector de nuvem.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versão 1.4.2 e posteriores  <br/> |Remove os certificados do servidor herdados do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda depois que você executa os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Somente a versão 1.4.2  <br/> |Reinstala o servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz:  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Somente a versão 1.4.2  <br/> |Renova os certificados para o Cloud Connector quando estão próximos de expirar ou já expiraram.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versão 1.4.2 e posteriores  <br/> |Redefine os servidores de autoridade de certificação para instalar um novo certificado de autoridade de certificação.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versão 2,1 e posterior  <br/> |Limpa as credenciais e solicita que você digite novamente todas as credenciais usadas para a implantação do conector de nuvem atual.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Pesquisa os logs de chamadas de entrada e saída no diretório de log do aparelho do Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Define o diretório de trabalho no servidor host do conector da nuvem. Todos os arquivos de implantação são armazenados nesse diretório.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Define a credencial da implantação do conector de nuvem atual.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica o caminho onde o certificado para o Servidor de Mediação ou para o Servidor de Borda é armazenado.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Define o diretório onde os arquivos de configuração em nível de site para o conector de nuvem serão armazenados. A pasta conterá o VHD de base e os arquivos de configuração do Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Baixa os bits do conector de nuvem e o arquivo MSI de sincronia.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Gera o log de chamadas de entrada e saída para um dispositivo do conector de nuvem.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Interrompe a geração do log de chamadas de entrada e saída para um aparelho de conector de nuvem.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Desconecta o dispositivo em execução e alterna para um dispositivo recém-implantado ou de backup.    <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Desinstala o dispositivo de conector de nuvem em execução do servidor host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Cancela o registro do dispositivo de conector de nuvem atual de um site PSTN na configuração do locatário online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versão 2.0 e posteriores  <br/> |Reinstala o servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz:  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versão 2.0 e posteriores  <br/> |Renova os certificados para o Cloud Connector quando estão próximos de expirar ou já expiraram.  <br/> |
   

