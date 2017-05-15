1	Hàm isDPHKM_KKCD_exist(String dPHKM_KKCD): boolean										
											
		boolean isDPHKM_KKCD_exist(String dPHKM_KKCD){									
			get database connection								
			get callable statement								
											
			execute procedure:  SELECT DPHKM_KKCD								
					FROM AUTMFOPM 						
					WHERE DPHKM_KKCD = @dPHKM_KKCD 						
											
			if have in database								
				return true;							
			else								
				 return fasle;							
											
			if there is any exception, catch and return false								
			close resultset								
			close statement								
			close connection								
		}									
											
2	Hàm isDPHKM_DEPO_exist(in String dPHKM_DEPO): boolean										
											
		boolean isDPHKM_DEPO_exist(in String dPHKM_DEPO){									
			get database connection								
			get callable statement								
											
			execute procedure:  SELECT DPHKM_DEPO								
					FROM AUTMFOPM 						
					WHERE DPHKM_DEPO = @dPHKM_DEPO 						
											
			if have in database								
				return true;							
			else								
				 return fasle;							
											
			if there is any exception, catch and return false								
			close resultset								
			close statement								
			close connection								
		}									
											
3	Hàm isDPHKM_PART_exist(in String dPHKM_PART): boolean										
											
		boolean isDPHKM_PART_exist(in String dPHKM_PART){									
			get database connection								
			get callable statement								
											
			execute procedure:  SELECT DPHKM_PART								
					FROM AUTITMCM						
					WHERE DPHKM_PART = @dPHKM_PART 						
											
			if have in database								
				return true;							
			else								
				 return fasle;							
											
			if there is any exception, catch and return false								
			close resultset								
			close statement								
			close connection								
		}									
											
4	Hàm isAUTDPHKM_exist(in AUTDPHKM autDPHKM): boolean										
											
		boolean  isAUTDPHKM_exist(in AUTDPHKM autDPHKM){									
			get database connection								
			get callable statement								
											
			execute procedure:  SELECT *								
					FROM AUTDPHKM						
					WHERE DPHKM_KKCD = @dPHKM_KKCD AND DPHKM_SSCD = @dPHKM_SSCD AND DPHKM_FORM = @dPHKM_FORM 						
						AND DPHKM_DEPO = @dPHKM_DEPO AND DPHKM_PART = @dPHKM_PART AND DPHKM_SYCD = @dPHKM_SYCD					
			if have in database								
				return true;							
			else								
				 return fasle;							
											
			if there is any exception, catch and return false								
			close resultset								
			close statement								
			close connection								
		}									
											
5	Hàm addAUTDPHKM(in AUTDPHKM autDPHKM): boolean										
											
		boolean addAUTDPHKM(in AUTDPHKM autDPHKM){									
			get database connection								
			get callable statement								
											
			execute procedure:  INSERT INTO AUTDPHKM VALUES(autDPHKM.getDPHKM_KKCD(), autDPHKM.getDPHKM_SSCD(), autDPHKM.getDPHKM_FORM(), 								
					autDPHKM.getDPHKM_DEPO(), autDPHKM.getDPHKM_PART(), autDPHKM.getDPHKM_SYCD())						
			result: true								
			return result								
			if there is any exception, catch , getMessage and return false								
			close resultset								
			close statement								
			close connection								
		}									

