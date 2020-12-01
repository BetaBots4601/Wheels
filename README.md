//# Wheels
//Code for wheels


import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.util.ElapsedTime;
import com.qualcomm.robotcore.util.Hardware;
import org.firstinspires.ftc.teamcode.BetaBotsHardware;
import static java.lang.Math.PI;


    public void loop() {
        double r = Math.hypot(gamepad1.left_stick_x, gamepad1.left_stick_y);
        double robotAngle = Math.atan2(gamepad1.left_stick_y, gamepad1.left_stick_x) - PI / 4;
        double rightX = gamepad1.right_stick_x;
        final double v1 = r * Math.sin(robotAngle) + rightX;
        final double v2 = r * Math.cos(robotAngle) - rightX;
        final double v3 = r * Math.cos(robotAngle) + rightX;
        final double v4 = r * Math.sin(robotAngle) - rightX;
        robot.frontLeftMotor.setPower(v1);
        robot.frontRightMotor.setPower(v2);
        robot.backLeftMotor.setPower(v3);
        robot.backRightMotor.setPower(v4);
    boolean G2leftBumper = gamepad2.left_bumper;
        boolean G2rightBumper = gamepad2.right_bumper;
     float G1leftStickx= gamepad1.left_stick_x;
     float G1leftSticky= gamepad1.left_stick_y;
   if (-G1leftStickx>0)
    { robot.frontLeftMotor.setPower(1);
    robot.frontRightMotor.setPower(1);
     robot.backLeftMotor.setPower(-1);
     robot.backRightMotor.setPower(-1);
    }
    else if (G1leftStickx<0)
       { robot.frontLeftMotor.setPower(-1);
        robot.frontRightMotor.setPower(-1);
         robot.backLeftMotor.setPower(1);
        robot.backRightMotor.setPower(1);
    }
    if (G1leftSticky>0);
     {   robot.frontLeftMotor.setPower(1);
        robot.frontRightMotor.setPower(-1);
         robot.backLeftMotor.setPower(1);
       robot.backRightMotor.setPower(-1);}
        
        if (-G1leftSticky<0);
    {    robot.frontLeftMotor.setPower(-1);
        robot.frontRightMotor.setPower(1);
         robot.backLeftMotor.setPower(-1);
        robot.backRightMotor.setPower(1);
        
