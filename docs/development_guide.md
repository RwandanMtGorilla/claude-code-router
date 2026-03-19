
# 1. 先停止当前服务                                                                                                                               
ccr stop                                                                                                                                          
                                                                                                                                                
# 2. 在项目根目录构建所有包                                                                                                                       
cd D:\projects\claude-code-router       
pnpm install
pnpm build                                                                                                                                        
              
# 3. 将本地项目链接到全局                                                                                                                         
npm link        
                                                                                                                                                
# 4. 启动服务   
ccr start                                                                                                                                         
              
执行完 npm link 后，全局的 ccr 命令就会指向你本地项目的 D:\projects\claude-code-router\dist\cli.js。                                              

之后每次改完代码，只需：                                                                                                                          
              
pnpm build && ccr restart                                                                                                                         
                                                                                                                                                
如果将来想恢复回 npm 安装的版本：                                                                                                                 
                                                                                                                                                
npm unlink -g @musistudio/claude-code-router                                                                                                      
npm install -g @musistudio/claude-code-router  