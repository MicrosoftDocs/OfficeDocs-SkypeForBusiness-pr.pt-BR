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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: A tabela a seguir lista os cmdlets do Skype for Business Cloud Connector Edition com uma breve descrição e links para mais informações.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359047"
---
# <a name="cloud-connector-cmdlet-reference"></a>Referência de cmdlet do Cloud Connector
 
> [!Important]
> O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online. Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

A tabela a seguir lista os cmdlets do Skype for Business Cloud Connector Edition com uma breve descrição e links para mais informações.
  
> [!NOTE]
> Você deve executar todos os cmdlets no computador host do Cloud Connector, e você deve executar a sessão do PowerShell como administrador. 
  
|**Nome do cmdlet**|**Descrição**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versão 1.4.2 e posterior  <br/> |Faz backup do serviço de autoridade de certificação em um arquivo e o salva na pasta AC no diretório de compartilhamento de site.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Cria um arquivo de disco rígido virtual (VHDX) base usando um arquivo ISO do Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante o conector de Cloud de implantação.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara o servidor host do Cloud Connector para o processo de atualização colocando-o no modo de manutenção. O dispositivo é "esvaziado"; ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas serão rejeitadas.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Sai do modo de manutenção de atualização no servidor host do Cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exporta uma configuração do Skype for Business Cloud Connector Edition para um arquivo local no servidor host do Skype for Business Cloud Connector Edition. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporta um arquivo de configuração de exemplo do Cloud Connector (. ini) para o diretório de dispositivos de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versão 1.4.2 e posterior  <br/> |Exporta o certificado de autoridade de certificação raiz para um arquivo local no servidor host do Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera o diretório de trabalho no servidor host do Cloud Connector. Todos os arquivos de implantação são armazenados nesse diretório.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Mostra o diretório atual em que os logs de um dispositivo do Cloud Connector são armazenados.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versão 2,1 e posterior  <br/> |Fornece informações de diagnóstico para o dispositivo do Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Retorna a credencial da implantação do Cloud Connector atual.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Retorna o caminho do arquivo do certificado externo para a implantação do Cloud Connector. O usuário prepara este certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Mostra o diretório atual onde os arquivos de configuração no nível do site estão armazenados. A pasta contém o VHD de base e os arquivos de instalação do Cloud Connector. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Mostra o diretório atual onde os logs no nível do site para o Cloud Connector são armazenados.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versão 2,0 e posterior  <br/> |Retorna a versão na instância do Cloud Connector. Get-CCVersion só pode ser usado na máquina host do Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versão 2,0 e posterior  <br/> |Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Instala o dispositivo do Cloud Connector, incluindo as máquinas virtuais do AD, do repositório de gerenciamento central, do servidor de mediação e do servidor de borda — no servidor host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtém informações de alta disponibilidade da configuração do locatário online e publica-as no dispositivo do Cloud Connector no servidor host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra as informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado para que possa ser implantado e gerenciado pelo serviço de gerenciamento do Cloud Connector. <br/> |
|[Remover-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versão 1.4.2 e posterior  <br/> |Remove o arquivo de backup do serviço de autoridade de certificação " \<SiteRootDirectory\> \CA\SFB CCE root. p12" da pasta AC sob o diretório de compartilhamento do site do Cloud Connector.  <br/> |
|[Remover-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versão 1.4.2 e posterior  <br/> |Remove certificados de servidor herdados do repositório de gerenciamento central, do servidor de mediação e do servidor de borda depois de executar os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Apenas a versão 1.4.2  <br/> |Reinstala o servidor AD de serviço de autoridade de certificação para criar um novo certificado de autoridade de certificação raiz.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Apenas a versão 1.4.2  <br/> |Renova os certificados para o Cloud Connector quando estão próximos de expirar ou já expiraram.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versão 1.4.2 e posterior  <br/> |Redefine os servidores de autoridade de certificação para instalar um novo certificado de autoridade de certificação.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versão 2,1 e posterior  <br/> |Limpa as credenciais e solicita que você insira novamente todas as credenciais usadas para a implantação do Cloud Connector atual.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Pesquisa os logs de chamadas de entrada e saída no diretório de log do dispositivo do Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Define o diretório de trabalho no servidor host do Cloud Connector. Todos os arquivos de implantação são armazenados nesse diretório.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Define a credencial da implantação do Cloud Connector atual.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica o caminho onde o certificado para o servidor de mediação ou servidor de borda está armazenado  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Define o diretório onde os arquivos de configuração no nível do site do Cloud Connector serão armazenados. A pasta conterá os arquivos de configuração do VHD e do Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Baixa os bits do Cloud Connector e o arquivo MSI de forma síncrona.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Gera o log de chamada de entrada e saída de um dispositivo do Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Para de gerar o log de chamada de entrada e saída de um dispositivo do Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Desconecta o dispositivo em execução e alterna para um dispositivo de implantação ou de backup recentemente implantado.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Desinstala o dispositivo do Cloud Connector em execução do servidor host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Cancela o registro do dispositivo do Cloud Connector atual de um site PSTN na configuração de locatário online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versão 2,0 e posterior  <br/> |Reinstala o servidor AD de serviço de autoridade de certificação para criar um novo certificado de autoridade de certificação raiz.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versão 2,0 e posterior  <br/> |Renova os certificados para o Cloud Connector quando estão próximos de expirar ou já expiraram.  <br/> |
   

