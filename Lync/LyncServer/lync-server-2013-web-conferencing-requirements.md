---
title: 'Lync Server 2013: requisitos da webconferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 404ce93e841bbbefd62498a1dbb3da664eb927ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518248"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Requisitos de Webconferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

Se você optou por habilitar a webconferência, será necessário planejar:

  - <span></span>  
    O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.

  - <span></span>  
    Integração com o servidor do Office Web Apps, que é necessário para compartilhar arquivos do PowerPoint durante uma conferência.

<div>

## <a name="file-store"></a>Repositório de Arquivos

O serviço de Webconferência do Lync Server 2013 armazena conteúdo compartilhado durante reuniões no repositório de arquivos. Como parte da implantação, você deve especificar um compartilhamento de arquivo a ser usado como o repositório de arquivos para o servidor Standard Edition ou o pool de front-ends Enterprise Edition. Você pode usar um repositório de arquivos existente ou pode especificar um novo compartilhamento de arquivos determinando o nome de domínio totalmente qualificado (FQDN) do servidor de arquivos em que o repositório estará localizado e um nome de pasta para o novo compartilhamento de arquivos.Para mais informações, consulte Construtor de Topologias – Definir o Repositório de Arquivos para o Front End. O serviço de webconferências criptografa o conteúdo antes de armazená-lo no repositório de arquivos.

O Lync Server 2013 oferece suporte ao uso de compartilhamentos de arquivo em DAS (armazenamento de conexão direta) ou em uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e em uma matriz redundante de discos independentes (RAID) para repositórios de arquivos. Após o assistente de implantação do Lync Server ter definido o local do compartilhamento de arquivos, o Lync Server cria uma estrutura de pastas dentro do compartilhamento de arquivos semelhante a:

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - Dataconferência

O serviço de webconferências então armazena conteúdo como slides do PowerPoint, quadros de comunicações, votações e anexos nas pastas CollabContent e CollabMetadata, localizadas na pasta WebServices.

O administrador deve definir permissões no compartilhamento de arquivos para que grupos do RTC tenham o acesso de leitura e gravação necessário.

<div>


> [!WARNING]  
> Se você encontrar erros com as permissões, abra o Construtor de Topologias, faça download e publique novamente a topologia existente. Publicar a topologia verificará as permissões do compartilhamento de arquivos e as redefinirá, se necessário.



</div>

Você pode usar as configurações a seguir para gerenciar como o conteúdo será armazenado para uma reunião:

  - **ContentGracePeriod**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define o quanto o conteúdo de webconferências permanecerá no servidor após o término da reunião.

  - **MaxContentStorageMb**, localizado em [set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), define a quantidade máxima de espaço de arquivo permitido para o armazenamento de conteúdo durante uma única reunião.

**MaxUploadFileSizeMb** não limita a configuração de carregamento de arquivo para o Lync Web App. O limite de carregamento de tamanho de arquivo para Lync Web App é definido como aproximadamente 30MB e é controlado pelo arquivo de web.config do IIS:/DataCollabWeb/Int \[ ext \] /Handler/web.config. Para configurar o limite de carregamento de tamanho de arquivo do Lync Web App, atualize `maxRequestLength` e `maxAllowedContentLength` no arquivo web.config conforme mostrado abaixo.

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

Você deve atualizar o arquivo de web.config para cada servidor de front-end.

</div>

<div>

## <a name="office-web-apps-server"></a>Servidor do Office Web Apps

Para usar esses novos recursos, os administradores devem instalar o Office Web Apps Server e devem configurar o Lync Server 2013 para se comunicar com o servidor do Office Web Apps. Esta documentação fornece informações sobre como configurar o Lync Server 2013 para funcionar com o servidor do Office Web Apps. O que esta documentação não fornece é informações sobre como instalar o Office Web Apps Server. Para obter detalhes sobre a instalação, consulte o site de implantação do Microsoft Office Web Apps em <https://go.microsoft.com/fwlink/p/?linkid=257525> . Esse guia inclui informações completas de pré-requisito para o servidor do Office Web Apps. Observe que o servidor do Office Web Apps deve ser instalado em um computador autônomo que não esteja executando o Lync Server, o SQL Server ou qualquer outro aplicativo de servidor. (Você não deve ter nenhuma versão do Office instalada nesse computador.) Qualquer computador usado para executar o servidor do Office Web Apps também deve ter um conjunto específico de software instalado (incluindo o .NET Framework 4,5 e o Windows PowerShell 3,0). Esses requisitos, juntamente com as informações sobre a configuração de certificados e os serviços de informações da Internet (IIS), são discutidos em detalhes no site de implantação do Microsoft Office Web Apps em <https://go.microsoft.com/fwlink/p/?linkid=257525> .

</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral da webconferência no Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Lista de verificação de implantação para Webconferência no Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

