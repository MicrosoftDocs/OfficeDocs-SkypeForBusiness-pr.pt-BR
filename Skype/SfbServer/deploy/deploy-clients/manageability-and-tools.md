---
title: Ferramentas e capacidade de gerenciamento do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para saber mais sobre ferramentas de gerenciamento para o Skype Room System.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093545"
---
# <a name="skype-room-system-manageability-and-tools"></a>Ferramentas e capacidade de gerenciamento do Sistema de Sala do Skype
 
Leia este tópico para saber mais sobre ferramentas de gerenciamento para o Skype Room System.
  
## <a name="administrative-portal"></a>Portal Administrativo

Para implantações locais do Skype for Business Server, você pode usar o portal administrativo do Sistema de Sala do Skype para gerenciar e monitorar ativamente as implantações do Sistema de Sala do Skype em sua organização.
  
Confira o artigo a seguir para obter mais detalhes:
  
- [Implantar o SRS v1 Administrative Web Portal no Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Lista de verificação do Exchange

- Confirme se a Descoberta Automática está configurada e um REGISTRO DNS A/CNAME interno está disponível para autodiscover.domain.com.
    
- Descoberta automática de ping (por exemplo, Ping Autodiscover.contoso.com).
    
- Teste seu serviço de Descoberta Automática com a Ferramenta analisador de Conectividade da Microsoft. Escolha o primeiro teste, "Não consigo fazer logoff com o Office Outlook".
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o Sistema de Sala do Skype (script de exemplo na parte inferior da página).
    
## <a name="skype-for-business-checklist"></a>Lista de verificação do Skype for Business

- Execute as seguintes ferramentas:
    
  - Analisador de Práticas Recomendadas do Skype for Business     
  - Ferramenta de Análise de Saúde do Skype for Business (Excel)    
  - Analisador de Conectividade do Skype for Business de 32 bits ou 64 bits
    
- Revisar [Novas ferramentas de solução de problemas e análise úteis para o Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365). Confirme se você tem um pool do Skype for Business e um servidor do Office Web Apps e pode compartilhar um deck do PowerPoint usando o cliente skype for Business.
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, habilita-a para o Skype for Business.
    
- Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.
    
## <a name="network"></a>Rede

- Certifique-se de ter uma conexão de rede com fio para o Sistema de Sala do Skype.
    
- Leia o Guia de Planejamento de Rede do Skype for Business.
    
- Solicite uma avaliação de rede do Skype for Business de um parceiro do Skype for Business.
    
- Leia os dados de desempenho capturados na Ferramenta de Análise de Saúde do Skype for Business (Excel).
    
- Execute a Ferramenta de Análise de Rede.
    
- Execute a Ferramenta de Diagnóstico de Pré-Chamada.
    
## <a name="skype-room-system-security"></a>Segurança do sistema de sala do Skype

O Sistema de Sala do Skype é um sistema incorporado que pode ser totalmente integrado em uma implantação do Windows, usando o modelo de segurança do Skype for Business, gerenciamento de direitos e ferramentas de gerenciamento, como SCOM. Os recursos incluem:
  
- Um Filtro de Gravação para impedir gravações de disco no modo de usuário 
    
- App Locker para impedir a execução de aplicativos não autorizados. Todas as portas USB estão desabilitadas no modo de usuário.
    
  - Nenhum aplicativo padrão ou visualizadores reside no hardware do Sistema de Sala do Skype. Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.
    
  - O computador do dispositivo executa o sistema operacional Windows Embedded Standard 7. Todo o hardware, incluindo dispositivos, é fornecido por parceiros OEM.
    
  - A junção de domínio opcional aos Serviços de Domínio do Active Directory (AD DS), habilitando o gerenciamento e o controle de contas de segurança locais.
    
- Você também pode gerenciar a conta de administrador local usando o Centro de administração do Skype for Business.
    
- O Sistema de Sala do Skype é atualizado por meio de processos padrão do Microsoft Update.
    
- O Sistema de Sala do Skype se conecta ao Skype for Business.
    
  - O Skype for Business usa criptografia de ponta a ponta e autorização para todos os modos de comunicação
    
  - O Sistema de Sala do Skype dá suporte aos padrões de segurança e conformidade do Skype for Business. Consulte [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) para obter mais informações.
    
## <a name="license"></a>Licença

Verifique se você usa um KMS para ativar software. Em caso afirmado, talvez seja necessário verificar ou adicionar a chave KMS do cliente skype for Business a ela. Se você não estiver usando KMS, solicite a chave de licenciamento por volume para o cliente MAK do Skype for Business.
  
## <a name="license-keys"></a>Chaves de licença

O Sistema de Sala do Skype executa o cliente da área de trabalho do Skype for Business em segundo plano. Se o Sistema de Sala do Skype for um membro de domínio, ele descobrirá seu KMS. (e se tiver a chave KMS de Licenciamento por Volume será ativada automaticamente). O Licenciamento por Volume também fornece um MAK, que você insinte à medida que exibe xxxxx-xxxxx-xxxxx-xxxxx-xxxxx. (Você precisa de acesso à Internet para ativar usando MAK, mas não KMS). Para obter mais informações, consulte Ativação de volume do Office 2013.
  
- Para inserir a chave MAK, vá para Ferramenta de Licenciamento do SRS configurações do \> OEM. Clique em Verificar Status. Quando o status diz "o produto não está ativado", digite a tecla.
    
- Se durante a ativação você receber um erro que diga "'O Serviço de Licenciamento de Software reportou que a chave do produto é inválida", verifique se:
    
  - A chave foi inserida corretamente.
    
  - Você entrou na chave MAK do Skype for Business e não em outra chave.
    
  - O sistema tem acesso à Internet.
    
- Você pode ativar por telefone, mas deve ter tentado ativar usando a Ferramenta de Licenciamento srs primeiro. Para ativar por telefone, inicie uma reunião de teste (não uma chamada de teste, pois é muito curta). No Assistente de Ativação do Office, selecione Ativação telefônica, chame a Microsoft, digite o número longo e insira uma resposta.
    
## <a name="certificate-authority"></a>Autoridade de Certificação

Confirme se a Autoridade de Certificação usada para emitir o certificado do Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade Lista de Revogação de Certificados.
  
Importe o arquivo Certificate (.crt) para o Sistema de Sala do Skype se estiver usando o Skype for Business Server. Ele é facilmente obtido do compartilhamento CertEnroll do servidor ca ou na pasta Raiz Confiável de qualquer computador ingressado no domínio.
  
## <a name="certificates"></a>Certificados

Verifique se a Autoridade de Certificação tem um caminho http para a Lista de Revogação de Certificados. Caso não seja, atualize sua AC para incluir um.
  
Instale certificados na configuração de administrador do Sistema de Sala do Skype em System Settings \> Certificate Manager. Você precisa da AC Raiz da Empresa para seu certificado interno.
  
Uma maneira de obter os certificados necessários é descobrir a AC que emitiu seus certificados. Para o Skype for Business Server, em um computador no Skype for Business, clique em Configurações \> Ferramentas \> de Discagem configurações de conferência. Isso abre uma página da Web protegida pela AC que emitiu os certificados internos. Clique no ícone Bloquear na barra de endereços do navegador para exibir um relatório de segurança. Clique em Exibir Certificados e examine a propriedade Ponto de Distribuição crl. O segundo parâmetro CN deve ser o nome do servidor da AC. Agora abra o Windows Explorer para esse endereço \\ \< CA Server Name \> \CertEnroll. Copie os dois arquivos .crl e o arquivo .crt para uma unidade flash e coloque-o no lado esquerdo da placa SMART.
  
Importe o arquivo .crt para o Sistema de Sala do Skype na pasta Autoridade de Certificação de Sala Confiável.
  
Importe os arquivos .crl no Sistema de Sala do Skype na pasta Autoridades intermediárias de certificados. (Você precisa alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para ver os arquivos).
  
Observação: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA do Skype for Business. Se não for, você não poderá compartilhar o PowerPoint em uma reunião. Verifique com a IT e obtenha os arquivos CRT e CRL do compartilhamento de rede da CA CertEnroll conforme explicado acima. 
  
A associação de domínio pode simplificar algumas coisas porque você pode tratar o Sistema de Sala do Skype como um sistema Windows e pode contar com o Active Directory para alguns dos aspectos do certificado. No entanto, é melhor gerenciar isso manualmente.
