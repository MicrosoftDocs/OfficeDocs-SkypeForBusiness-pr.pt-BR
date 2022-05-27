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
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676163"
---
# <a name="cloud-connector-cmdlet-reference"></a>Referência de cmdlet do Cloud Connector

> [!Important]
> O Cloud Connector Edition será desativado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto](/MicrosoftTeams/direct-routing-landing-page).

A tabela a seguir lista os Skype for Business Cloud Connector Edition cmdlets com uma breve descrição e links para mais informações.
  
> [!NOTE]
> Você deve executar todos os cmdlets no computador host do Cloud Connector e executar a sessão do PowerShell como Administrador. 
  
|Nome do cmdlet**|Descrição|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> Versão 1.4.2 e posterior|Faz backup do serviço de autoridade de certificação em um arquivo e o salva na pasta ac no diretório de compartilhamento do site.|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|Cria um VHDX (arquivo de disco rígido virtual) base usando um arquivo ISO Windows Server 2012 R2 fornecido pelo cliente. O arquivo VHDX será usado durante a implantação do Conector doCloud.|
|[Enter-CcUpdate](enter-ccupdate.md)|Prepara o servidor host do Cloud Connector para o processo de atualização colocando-o no modo de manutenção. O aparelho está "esvaziado"; ou seja, todas as chamadas existentes serão concluídas, mas novas chamadas serão rejeitadas.|
|[Exit-CcUpdate](exit-ccupdate.md)|Sai do modo de manutenção de atualização no servidor host do Cloud Connector.|
|[Export-CcConfiguration](export-ccconfiguration.md)|Exporta uma configuração Skype for Business Cloud Connector Edition para um arquivo local no servidor Skype for Business Cloud Connector Edition host.|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|Exporta um arquivo de configuração de exemplo do Cloud Connector (.ini) para o diretório do dispositivo de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> Versão 1.4.2 e posterior|Exporta o certificado de autoridade de certificação raiz para um arquivo local no servidor host do Cloud Connector.|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Recupera o diretório de trabalho no servidor host do Cloud Connector. Todos os arquivos de implantação são armazenados nesse diretório.|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Mostra o diretório atual em que os logs de um dispositivo do Cloud Connector são armazenados.|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> Versão 2.1 e posterior|Fornece informações de diagnóstico para o dispositivo Cloud Connector.|
|[Get-CcCredential](get-cccredential.md)|Retorna a credencial da implantação atual do Cloud Connector.|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|Retorna o caminho do arquivo de certificado externo para a implantação do Cloud Connector. O usuário prepara esse certificado.|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|Mostra o diretório atual em que os arquivos de configuração no nível do site são armazenados. A pasta contém os arquivos de instalação base do VHD e do Cloud Connector. Essa pasta deve ser compartilhada com todos os outros dispositivos de um site do Cloud Connector.|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Mostra o diretório atual em que os logs de nível de site do Cloud Connector são armazenados.|
|[Get-CcVersion](get-ccversion.md) <p> Versão 2.0 e posterior|Retorna a versão na instância do Cloud Connector. Get-CCVersion pode ser usado somente no computador host do Cloud Connector.|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> Versão 2.0 e posterior|Importa a configuração Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.|
|[Install-CcAppliance](install-ccappliance.md)|Instala o dispositivo do Cloud Connector, incluindo o AD, o Repositório de Gerenciamento Central, o Servidor de Mediação e as máquinas virtuais do Servidor de Borda, no servidor host.|
|[Publish-CcAppliance](publish-ccappliance.md)|Obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo Cloud Connector no servidor host.|
|[Register-CcAppliance](register-ccappliance.md)|Registra informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes que possa ser implantado e gerenciado pelo serviço de gerenciamento do Cloud Connector.|
|[Remover-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> Versão 1.4.2 e posterior|Remove o arquivo de backup do serviço de autoridade de certificação "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" na pasta CA no diretório de compartilhamento de site do Cloud Connector.|
|[Remover-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> Versão 1.4.2 e posterior|Remove certificados de servidor herdados no Repositório de Gerenciamento Central, servidor de mediação e servidor de borda depois de executar os cmdlets Renew-CcCACertificate ou Renew CcServerCertificate.|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> Versão 1.4.2 somente|Reinstala o Servidor do AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz.|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> Versão 1.4.2 somente|Renova os certificados para o Cloud Connector quando eles estão próximos da expiração ou já expiraram.|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> Versão 1.4.2 e posterior|Redefine os servidores de autoridade de certificação para instalar um novo certificado de autoridade de certificação.|
|[Restore-CcCredentials](restore-cccredentials.md) <p> Versão 2.1 e posterior|Limpa as credenciais e solicita que você insira novamente todas as credenciais usadas para a implantação atual do Cloud Connector.|
|[Search-CcLog](search-cclog.md)|Pesquisa os logs de chamadas de entrada e saída no diretório de log do dispositivo do Cloud Connector|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Define o diretório de trabalho no servidor host do Cloud Connector. Todos os arquivos de implantação são armazenados nesse diretório.|
|[Set-CcCredential](set-cccredential.md)|Define a credencial da implantação atual do Cloud Connector.|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|Especifica o caminho em que o certificado para o Servidor de Mediação ou Servidor de Borda está armazenado|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Define o diretório em que os arquivos de configuração no nível do site para o Cloud Connector serão armazenados. A pasta conterá os arquivos de configuração base do VHD e do Cloud Connector.|
|[Start-CcDownload](start-ccdownload.md)|Baixa os bits do Cloud Connector e o arquivo msi de forma síncrona.|
|[Start-CcLogging](start-cclogging.md)|Gera o log de chamadas de entrada e saída para um dispositivo do Cloud Connector.|
|[Stop-CcLogging](stop-cclogging.md)|Para de gerar o log de chamadas de entrada e saída para um dispositivo do Cloud Connector.|
|[Switch-CcVersion](switch-ccversion.md)|Desconecta o dispositivo em execução e alterna para um dispositivo de backup ou recém-implantado.|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|Desinstala o dispositivo Cloud Connector em execução do servidor host.|
|[Unregister-CcAppliance](unregister-ccappliance.md)|Cancela o registro do dispositivo do Cloud Connector atual de um site PSTN na configuração de locatário online.|
|[Update-CcCACertificate](update-cccacertificate.md) <p> Versão 2.0 e posterior|Reinstala o Servidor do AD do Serviço de Autoridade de Certificação para criar um novo certificado de autoridade de certificação raiz.|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> Versão 2.0 e posterior|Renova os certificados para o Cloud Connector quando eles estão próximos da expiração ou já expiraram.|
