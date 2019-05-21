---
title: Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.
ms.openlocfilehash: 4ae57457eb244e7cf72183bfadba0bd0b89d44a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293540"
---
# <a name="skype-room-system-manageability-and-tools"></a>Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype
 
Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.
  
## <a name="administrative-portal"></a>Portal Administrativo

Para implantações locais do Skype for Business Server, você pode usar o portal administrativo do sistema de sala do Skype para gerenciar e monitorar ativamente implantações do sistema de sala do Skype dentro da sua organização.
  
Para obter mais detalhes, consulte o artigo a seguir:
  
- [Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

O sistema de sala do Skype pode ser monitorado por meio do SCOM (System Center Operations Manager) baixando o [pacote de gerenciamento do sistema de sala do Skype](https://www.microsoft.com/download/details.aspx?id=42320) e instalando-o em seu servidor do SCOM. Você pode usar o SCOM para definir alertas, monitorar a integridade do sistema de salas da Skype, gerar relatórios de tempo de atividade e muito mais. O sistema de salas da Skype vem com um agente de monitoramento pré-instalado que pode ser configurado para apontar para o servidor do SCOM. Consulte o guia de instalação fornecido pelo fabricante do seu sistema de sala do Skype para saber como configurar o agente de monitoramento no sistema de sala do Skype.
  
## <a name="exchange-checklist"></a>Verificação do Exchange

- O item Confirmar a Descoberta Automática é configurado e um DNS A/CNAME RECORD está disponível para autodiscover.domain.com.
    
- Executar o ping de descoberta automática (por exemplo, Ping Autodiscover.contoso.com).
    
- Teste seu serviço de Descoberta Automática com a Ferramenta de Análise de Conectividade da Microsoft. Escolher o primeiro teste, "não é possível fazer logon com o Office Outlook".
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o sistema de sala da Skype (exemplo de script na parte inferior da página).
    
## <a name="skype-for-business-checklist"></a>Lista de verificação do Skype for Business

- Executar as seguintes ferramentas:
    
  - Analisador de práticas recomendadas do Skype for Business     
  - Ferramenta de análise de integridade do Skype for Business (Excel)    
  - Analisador de conectividade do Skype for Business 32 bits ou 64 bits
    
- Revise [novas ferramentas úteis de solução de problemas e análise para o Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Confirme se você tem um pool do Skype for Business e um servidor do Office Web Apps e pode compartilhar uma apresentação do PowerPoint usando o cliente Skype for Business.
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, habilite-a para o Skype for Business.
    
- Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.
    
## <a name="network"></a>Rede

- Verifique se você tem uma conexão de rede com fio para o sistema de sala da Skype.
    
- Leia o guia de planejamento de rede para o Skype for Business.
    
- Solicite uma avaliação de rede do Skype for Business a partir de um parceiro do Skype for Business.
    
- Leia os dados de desempenho capturados na ferramenta de análise de integridade do Skype for Business (Excel).
    
- Execute a Ferramenta de Análise de Rede.
    
- Execute a Ferramenta de Pré-diagnóstico de chamada.
    
## <a name="skype-room-system-security"></a>Segurança do sistema de sala do Skype

O sistema de salas da Skype é um sistema integrado que pode ser totalmente integrado a uma implantação do Windows, usando o modelo de segurança do Skype for Business, o gerenciamento de direitos e as ferramentas de gerenciamento, como o SCOM. Os recursos incluem:
  
- Um Filtro de Gravação para impedir gravações de disco no modo usuário 
    
- Bloqueador de aplicativos para impedir que aplicativos não autorizados sejam executados. Todas as portas USB estão desabilitadas no modo usuário.
    
  - Nenhum aplicativo ou Visualizador padrão reside no hardware do sistema de sala do Skype. Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.
    
  - O PC executa o sistema operacional Padrão 7 Incorporado do Windows. Todo o hardware, incluindo dispositivos, é fornecido pelos parceiros de OEM.
    
  - Ingresso Opcional de Domínio para Serviços de Domínio do Active Directory (AD DS), permitindo gerenciamento e controle de contas de segurança local.
    
- Você também pode gerenciar a conta de administrador local usando o centro de administração do Skype for Business.
    
- O sistema de sala do Skype é atualizado por meio de processos padrão do Microsoft Update.
    
- O sistema da sala Skype se conecta ao Skype for Business.
    
  - O Skype for Business usa a autorização e a criptografia ponto a ponto para todos os modos de comunicação
    
  - O sistema de sala da Skype é compatível com os padrões de conformidade e segurança do Skype for Business. Para obter mais informações, consulte [planejar a segurança no Skype for Business Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Licença

Verify that you use a KMS for activating software. Em caso afirmativo, talvez seja necessário verificar ou adicionar a chave KMS do cliente Skype for Business. Se você não estiver usando o KMS, solicite a chave de licenciamento por volume para a MAK do cliente Skype for Business.
  
## <a name="license-keys"></a>Chaves de Licença

O sistema de sala do Skype executa o cliente de desktop do Skype for Business em segundo plano. Se o sistema de sala da Skype for um membro do domínio, ele descobrirá seu KMS. (e se tiver a chave KMS de licenciamento por volume, ela será ativada automaticamente). O Licenciamento do Volume também oferece um MAK, que você digita quando ele exibe xxxxx-xxxxx-xxxxx-xxxxx. (Você precisa ter acesso à Internet para ativar utilizando o MAK, mas não o KMS). Para obter mais informações, consulte ativação do Volume do Office 2013.
  
- Para inserir a chave MAK, acesse a ferramenta \> de licenciamento SRS de configurações de OEM. Clique em Verificar Estado. Quando o status diz "produto não está ativado", insira a chave.
    
- Se durante a ativação você receber um erro dizendo que "' o serviço de licenciamento de software informou que a chave do produto é inválida", verifique se:
    
  - A chave foi inserida corretamente.
    
  - Você inseriu a chave MAK do Skype for Business e não outra chave.
    
  - O sistema tem acesso à Internet.
    
- Você pode ativá-lo por telefone, mas deve tentar ativá-lo usando primeiramente a Ferramenta de Licenciamento de SRS. Para ativá-lo por telefone, inicie uma reunião de teste (não uma chamada de teste, pois ela é muito curta). No Assistente para ativação do Office, selecione ativação por telefone, ligue para a Microsoft, digite o número longo e digite uma resposta.
    
## <a name="certificate-authority"></a>Autoridade de Certificação

Confirme se a Autoridade de Certificação utilizada para emitir o certificado do Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade de Listas de Revogação de Certificados.
  
Importe o arquivo de certificado (. CRT) para o sistema de sala da Skype se estiver usando o Skype for Business Server. Pode ser facilmente obtido no compartilhamento CertEnroll do servidor CA ou na pasta Raiz Confiável de qualquer PC que participe do domínio.
  
## <a name="certificates"></a>Certificados

Verifique se sua Autoridade de Certificação tem um caminho de http para a lista de Revogação de Certificados. Se não tiver, atualize a sua CA para incluir um.
  
Instale certificados na configuração do administrador do sistema de salas da Skype, em \> Gerenciador de certificados de configurações do sistema. Você precisa de um CA de Raiz Corporativa para seu certificado interno.
  
Uma maneira de obter os certificados que você precisa consiste em descobrir a CA que emitiu seus certificados. Para o Skype for Business Server, em um PC no Skype for Business, clique \> em \> ferramentas de configurações, configurações de conferência discada. Isso abre uma página da Web protegida pela autoridade de certificação que emitiu os certificados internos. Clique no ícone de Cadeado na barra de endereço do navegador para exibir um relatório de segurança. Clique em Exibir Certificados e examine a propriedade do Ponto de Distribuição de CRL. O segundo parâmetro de CN deve ser o nome do servidor de CA. Agora, abra o Windows Explorer para \\ \< esse nome \>de servidor de CA de endereço \CertEnroll. Copie o dois arquivos .crl e o arquivo .crt em uma unidade flash e coloque-os no lado esquerdo da placa SMART.
  
Importe o arquivo. CRT para o sistema de sala do Skype na pasta de autoridade de certificação de sala confiável.
  
Importe os arquivos. CRL no sistema de sala do Skype na pasta autoridades de certificação intermediárias. (Será necessário alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para visualizar os arquivos.)
  
Observação: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA que o Skype for Business. Caso contrário, você não poderá compartilhar PowerPoint em uma reunião. Verifique com o departamento de TI e permita que os arquivos CRT e CRL fora da rede de CA compartilhem CertEnroll como explicado acima. 
  
A associação de domínio pode simplificar alguns itens porque você pode tratar o sistema de sala da Skype como um sistema do Windows e pode depender do Active Directory para alguns dos aspectos do certificado. No entanto, é melhor gerenciar este assunto manualmente.
  

