# semana19back


Semana 19 Atividade adaptada: Fluxo de arquitetura

3. Parte Prática – Plano da Solução

Problema	Solução Escolhida	Por que ajuda?	Exemplo de ferramenta/conceito
Site lento em períodos de muito acesso	Balanceamento de carga e Cache.	Distribui as requisições entre múltiplos servidores, evitando sobrecarga em uma única instância, e acelera as respostas guardando dados comuns na memória.	Nginx (como Load Balancer) e Redis / Memcached.
Arquivos demorando para carregar	Compressão de arquivos e CDN.	Reduz o tamanho de arquivos de texto (HTML, CSS, JS) trafegados na rede, otimizando o tempo de transferência e o consumo de banda.	Algoritmos GZIP / Brotli e Cloudflare.
Erros chegando ao ambiente de produção	Integração Contínua (CI) com testes automatizados.	Roda uma bateria de testes (unitários e de integração) a cada modificação de código, bloqueando atualizações que quebrem o sistema.	GitHub Actions ou GitLab CI/CD (etapa de Test).
Deploy muito dependente de etapas manuais	Entrega Contínua / Deploy Contínuo (CD).	Elimina a necessidade de intervenção humana para subir o código, reduzindo falhas operacionais e acelerando o tempo de lançamento.	Jenkins ou GitHub Actions (etapa de Deploy).
Usuários acessando dados além do necessário	Controle de acesso baseado em papéis (RBAC).	Garante que cada colaborador ou microsserviço possua apenas as permissões estritamente necessárias para exercer sua função de negócio.	Princípio do menor privilégio (Garantia de GRANT/REVOKE no SQL).
Necessidade de identificar acessos suspeitos	Auditoria e Monitoramento de Banco de Dados.	Registra quem acessou qual dado e quando, disparando alertas automáticos em caso de queries anômalas ou fora do padrão esperado.	Logs de auditoria nativos (ex: pgAudit para PostgreSQL) ou ferramentas como Datadog.
Parte 4: Visual Fluxo de arquitetura back end



5. Perguntas Dissertativas Integradas

1. Qual é a importância do cache em servidores web?
Resposta: O cache ajuda a deixar o site mais rápido, pois guarda temporariamente informações que são acessadas com frequência. Assim, o servidor não precisa buscar os mesmos dados toda hora.

2. Como o balanceamento de carga pode melhorar o desempenho de uma aplicação?
Resposta: Ele distribui as requisições entre vários servidores. Dessa forma, nenhum servidor fica muito sobrecarregado e a aplicação consegue funcionar melhor.

3. Quais fatores podem ser considerados ao escolher entre Nginx e Apache?
Resposta: É importante considerar a quantidade de acessos e o tipo de aplicação. O Nginx é conhecido por ser rápido e consumir poucos recursos, enquanto o Apache possui várias opções de configuração.

4. Como a compressão de arquivos pode ajudar na performance de um servidor?
Resposta: A compressão diminui o tamanho dos arquivos enviados pela internet. Com arquivos menores, o carregamento fica mais rápido e o uso da internet também diminui.

5. Quais são os principais benefícios de implementar CI/CD em um projeto?
Resposta: O CI/CD ajuda a automatizar os processos do projeto, facilita a entrega de novas versões e diminui a chance de erros causados por tarefas manuais.

6. Como um pipeline de CI/CD ajuda a detectar erros antes do deploy?
Resposta: O pipeline realiza testes automaticamente antes de colocar o sistema em produção. Se algum teste apresentar erro, o deploy pode ser interrompido até o problema ser corrigido.

7. Que fatores devem ser considerados ao escolher uma ferramenta de CI/CD, como Jenkins, GitHub Actions ou GitLab CI/CD?
Resposta: É importante analisar qual ferramenta combina melhor com o projeto, a facilidade de uso, as integrações disponíveis e os recursos que a equipe precisa.

8. Como você estruturaria um pipeline simples para diminuir a chance de erros em produção?
Resposta: Eu faria o pipeline com as etapas de Build, Test, Staging e Deploy. Primeiro o código seria preparado, depois testado, validado em um ambiente de teste e só depois enviado para produção.

9. Por que o princípio do menor privilégio é importante na segurança de um banco de dados?
Resposta: Ele limita o acesso de cada usuário somente ao que ele realmente precisa. Assim, caso uma conta seja invadida, os danos podem ser menores.

10. Qual é a diferença entre proteger dados em trânsito e dados em repouso por meio de criptografia?
Resposta: Dados em trânsito são protegidos enquanto estão sendo enviados pela rede. Já os dados em repouso são protegidos enquanto estão armazenados no banco de dados ou em outros dispositivos.

11. Como um sistema de auditoria pode ajudar a identificar atividades suspeitas no banco de dados?
Resposta: A auditoria registra os acessos e as ações feitas no banco de dados. Com esses registros, é possível identificar atividades diferentes ou suspeitas.

12. Cite práticas que podem prevenir acessos não autorizados aos dados.
Resposta: Algumas práticas são usar senhas fortes, autenticação em dois fatores, criptografia, firewall e limitar o acesso dos usuários aos dados necessários.

6. Síntese Final

Como servidores otimizados, CI/CD e segurança de banco de dados trabalham juntos para tornar uma aplicação mais confiável?

Resposta: Os servidores otimizados ajudam a aplicação a funcionar de forma rápida e estável. O CI/CD ajuda a testar e atualizar o sistema com mais segurança. Já a segurança do banco de dados protege as informações. Juntos, eles deixam a aplicação mais rápida, segura e confiável.
