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
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: A tabela a seguir lista os Skype for Business Cloud Connector Edition cmdlets com uma breve descrição e links para mais informações.
ms.openlocfilehash: 19fc33912075e7737a4fa7fc242e74dd1de92289
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583725"
---
# <a name="cloud-connector-cmdlet-reference"></a>Referência de cmdlet do Cloud Connector
 
> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

A tabela a seguir lista os Skype for Business Cloud Connector Edition cmdlets com uma breve descrição e links para mais informações.
  
> [!NOTE]
> Você deve executar todos os cmdlets na máquina host do Cloud Connector e executar a sessão do PowerShell como Administrador. 
  
|**Nome do cmdlet**|**Descrição**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Versão 1.4.2 e posterior  <br/> |Faz o back up the certification authority service to a file and saves it to the CA folder under the site share directory.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Cria um arquivo de disco rígido virtual base (VHDX) usando um cliente fornecido Windows Server 2012 arquivo ISO R2. O arquivo VHDX será usado durante a implantação doCloud Connector.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Prepara o servidor host do Cloud Connector para o processo de atualização colocando-o no modo de manutenção. O dispositivo está "esvaziado"; ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas serão rejeitadas.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Sai do modo de manutenção de atualização no servidor host do Cloud Connector.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exporta uma configuração Skype for Business Cloud Connector Edition para um arquivo local no servidor Skype for Business Cloud Connector Edition host. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exporta um arquivo de configuração de exemplo do Cloud Connector (.ini) para o diretório do dispositivo de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Versão 1.4.2 e posterior  <br/> |Exporta o certificado de AC raiz para um arquivo local no servidor host do Cloud Connector.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Recupera o diretório de trabalho no servidor host do Cloud Connector. Todos os arquivos de implantação são armazenados neste diretório.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Mostra o diretório atual onde os logs de um dispositivo do Cloud Connector são armazenados..  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Versão 2.1 e posterior  <br/> |Fornece informações de diagnóstico para o dispositivo Cloud Connector.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Retorna a credencial da implantação atual do Cloud Connector.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Retorna o caminho do arquivo de certificado externo para a implantação do Cloud Connector. O usuário prepara esse certificado.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Mostra o diretório atual onde os arquivos de configuração no nível do site são armazenados. A pasta contém os arquivos de instalação base VHD e Cloud Connector. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do Cloud Connector.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Mostra o diretório atual onde os logs de nível do site para o Cloud Connector estão armazenados.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Versão 2.0 e posterior  <br/> |Retorna a versão na instância do Cloud Connector. Get-CCVersion pode ser usado apenas no computador host do Cloud Connector.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Versão 2.0 e posterior  <br/> |Importa a configuração Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Instala o dispositivo do Cloud Connector, incluindo o AD, o Armazenamento de Gerenciamento Central, o Servidor de Mediação e as máquinas virtuais do Servidor de Borda no servidor host.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo do Cloud Connector no servidor host. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registra informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes de poder ser implantado e gerenciado pelo serviço de gerenciamento do Cloud Connector. <br/> |
|[Remover-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Versão 1.4.2 e posterior  <br/> |Remove o arquivo de backup do serviço de autoridade de certificação " \<SiteRootDirectory\> \CA\SfB CCE Root.p12" na pasta CA no diretório de compartilhamento de sites para o Cloud Connector.  <br/> |
|[Remover-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Versão 1.4.2 e posterior  <br/> |Remove certificados de servidor herdados no Armazenamento de Gerenciamento Central, Servidor de Mediação e Servidor de Borda depois de executar os cmdlets Renew-CcCACertificate ou Renovar CcServerCertificate.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Versão 1.4.2 somente  <br/> |Reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AC raiz.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Versão 1.4.2 somente  <br/> |Renova os certificados para o Cloud Connector quando eles estão próximos da expiração ou já expiraram.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Versão 1.4.2 e posterior  <br/> |Redefine os servidores de autoridade de certificação para instalar um novo certificado de autoridade de certificação.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Versão 2.1 e posterior  <br/> |Limpa as credenciais e solicita que você insira todas as credenciais usadas para a implantação atual do Cloud Connector.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Pesquisa os logs de chamadas de entrada e saída no diretório de log de dispositivos do Cloud Connector  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Define o diretório de trabalho no servidor host do Cloud Connector. Todos os arquivos de implantação são armazenados neste diretório.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Define a credencial da implantação atual do Cloud Connector.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Especifica o caminho onde o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Define o diretório onde os arquivos de configuração de nível de site para o Cloud Connector serão armazenados. A pasta conterá os arquivos de configuração base VHD e Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Baixa os bits do Cloud Connector e o arquivo msi de forma síncrona.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Gera o log de chamadas de entrada e saída para um dispositivo do Cloud Connector.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Para de gerar o log de chamadas de entrada e saída para um dispositivo do Cloud Connector.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Desconecta o dispositivo em execução e alterna para um dispositivo recém-implantado ou de backup.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Desinstala o dispositivo do Cloud Connector em execução do servidor host.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Não faz o registro do dispositivo do Cloud Connector atual de um site PSTN na configuração de locatário online.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Versão 2.0 e posterior  <br/> |Reinstala o Servidor AD do Serviço de Autoridade de Certificação para criar um novo certificado de AC raiz.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Versão 2.0 e posterior  <br/> |Renova os certificados para o Cloud Connector quando eles estão próximos da expiração ou já expiraram.  <br/> |
