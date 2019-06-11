---
title: 'Lync Server 2013: requisitos da webconferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Requisitos da webconferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

Se você optou por habilitar a webconferência, será necessário planejar:

  - <span></span>  
    O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.

  - <span></span>  
    Integração com o Servidor do Office Web Apps, necessária para compartilhar arquivos do PowerPoint durante uma conferência.

<div>

## <a name="file-store"></a>Repositório de Arquivos

O serviço de Webconferência do Lync Server 2013 armazena conteúdo compartilhado durante reuniões no repositório de arquivos. Como parte da implantação, você deve especificar um compartilhamento de arquivos a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de front-end da edição Enterprise. É possível usar um compartilhamento de arquivos existente para o repositório de arquivos ou definir um novo especificando o FQDN (nome de domínio totalmente qualificado) do servidor de arquivos no qual o compartilhamento de arquivos deve estar localizado e um nome de pasta para o novo compartilhamento de arquivos.Para obter mais informações, consulte Construtor de topologias – defina o repositório de arquivos do front-end. O serviço de webconferências criptografa o conteúdo antes de armazená-lo no repositório de arquivos.

O Lync Server 2013 oferece suporte ao uso de compartilhamentos de arquivos em DAS (armazenamento de conexão direta) ou de uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e um conjunto redundante de discos independentes (RAID) para armazenamentos de arquivos. Depois que o assistente de implantação do Lync Server tiver definido o local do compartilhamento de arquivos, o Lync Server criará uma estrutura de pastas dentro do compartilhamento de arquivos semelhante a:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

O serviço de webconferências então armazena conteúdo como slides do PowerPoint, quadros de comunicações, votações e anexos nas pastas CollabContent e CollabMetadata, localizadas na pasta WebServices.

O administrador deve definir permissões no compartilhamento de arquivos para que os grupos RTC tenham o acesso de leitura e gravação necessário.

<div>


> [!WARNING]  
> Se você encontrar erros com as permissões, abra o construtor de topologias, baixe e Republique novamente a topologia existente. A publicação da topologia verificará as permissões de compartilhamento de arquivos e as redefinirá, se necessário.



</div>

Você pode usar as configurações a seguir para gerenciar como o conteúdo é armazenado para uma reunião:

  - **ContentGracePeriod**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define o tempo que o conteúdo da webconferência permanecerá no servidor após o término da reunião.

  - **MaxContentStorageMb**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define o valor máximo de espaço de arquivo permitido para o armazenamento de conteúdo durante uma única reunião.

**MaxUploadFileSizeMb** não limita a configuração de carregamento de arquivo do Lync Web App. O limite de carregamento do tamanho do arquivo do Lync Web App é definido como aproximadamente 30MB e é controlado pelo arquivo Web. config do\[IIS\]:/DataCollabWeb/int ext/Handler/Web.config. Para configurar o limite de carregamento de tamanho do arquivo para o Lync `maxRequestLength` Web `maxAllowedContentLength` app, atualize e no arquivo Web. config, como mostrado a seguir.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Você deve atualizar o arquivo Web. config para cada servidor front-end.

</div>

<div>

## <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para usar esses novos recursos, os administradores devem instalar o Office Web Apps Server e devem configurar o Lync Server 2013 para se comunicar com o servidor do Office Web Apps. Esta documentação fornece informações sobre como configurar o Lync Server 2013 para trabalhar com o servidor do Office Web Apps. O que essa documentação não fornece é informações sobre como instalar o Office Web Apps Server. Para obter detalhes sobre a instalação, consulte o site de implantação do <http://go.microsoft.com/fwlink/p/?linkid=257525>Microsoft Office Web Apps em. Esse guia inclui informações completas de pré-requisito para o Office Web Apps Server. Observe que o Office Web Apps Server deve ser instalado em um computador autônomo que não esteja executando o Lync Server, o SQL Server ou qualquer outro aplicativo de servidor. (Você não deve ter qualquer versão do Office instalada nesse computador.) Qualquer computador usado para executar o Office Web Apps Server também deve ter um conjunto específico de softwares instalado (incluindo .NET Framework 4,5 e Windows PowerShell 3,0). Esses requisitos, juntamente com informações sobre a configuração de certificados e serviços de informações da Internet (IIS), são discutidos em detalhes no site de implantação <http://go.microsoft.com/fwlink/p/?linkid=257525>do Microsoft Office Web Apps em.

</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral da Web conferência no Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Lista de verificação da implantação para Webconferência no Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

